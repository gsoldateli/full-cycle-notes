# Comunicação entre sistemas

É uma das áreas mais importantes quando estamos falando de arquitetura de software. Desenvolvedores geralmente usam um ou dois modos de comunicações em seus sistemas, e isso pode ser um grande erro dependendo da situação.

Neste módulo vamos refletir sobre como escolher a melhor forma de comunicação para o seu projeto.

### Introdução

- Vamos notar que nem sempre a comunicação síncrona é necessária.
- Quanto mais síncrona a comunicação da aplicação, mais dependente e menos resiliente ela fica.
- A grande sabedoria de um desenvolvedor hoje em dia é saber decidir/decifrar qual a melhor forma de comunicação para seu contexto.
- Nem todas comunicações feitas entre micro-serviços precisam ser feitas via REST.
    - O REST envia requisição e espera resposta, isso pode gerar muita lentidão.


### Comunicação Sincrona vs. Assíncrona.

Geralmente cada microserviço tem um banco de dados próprio. Isso gera muita independencia.

Imagina um microsserviço de **produtos** e outro de **checkout**.

Você está comprando o produto, o checkout precisa apenas do nome, preço do produto.

checkout copia os dados necessários para o banco dele.

Agora se o microsserviço de produtos cair, o checkout continua funcionando.

Agora imagine que o produto cadastrado no microsserviço de produtos estava com erro de escrita no nome.

A correção é feita no microsserviço de produto, mas e o checkout como fica?

Essa diferença é chamada de **inconsistência eventual**, nome este porque logo logo o produto vai ser atualizado no checkout também através de um message broker.

> Inconsistência eventual é o preço a se pagar para se ter micro serviços independentes.

No facebook isso também acontece, se trocar seu nome, e depois ir num grupo, vai ver que ele não trocou no mesmo momento.



## REST

- Raros os devs que sabem que o REST é mais do que verbos e status codes organizados.
- REST = **RE**presentational **S**tate of **T**ransfer
- Surgiu em 200 por Roy Fielding em uma dissertação de doutorado.
- Simplicidade.
- Stateless, cada requisição é independente.
- Cacheável


### REST: Níveis de maturidade (Richardson Maturity Model

- Nível 0: The swamp of POX. (RPC)
- Nível 1: Utilização de resources
    - ![Resources](https://i.imgur.com/gcMy4qi.png)
- Nível 2: Verbos HTTP
    - Quando se utiliza o verbo correto para a operação correta.
        - GET: Recuperar informação
        - POST: Inserir
        - PUT: Alterar
        - DELETE: Remover
- Nível 3: HATEOAS - Hypermedia as the Engine Application State
    - A sua requisição é processada, e além do retorno normal, também trás a lista de operações que você pode fazer depois com base na operação executou.
        - ![HATEOAS](https://i.imgur.com/zaAPbVF.png)
    - Nesse estado a API ajuda os outros desenvolvedores a tirarem o melhor dela, é a base da internet, documentos linkando outros documentos.

### Method e Content Negotiation

**REST: Como é uma boa API?**

- #1 - Utiliza URIs unicas para serviços e itens que expostos a estes serviços.
- #2 - Utiliza todos os VERBOS HTTP para realizar as operações em seus recursos, incluindo caching.
- #3 - Provê links relacionais para os recursos, exemplificando o que pode ser feito.

Maioria esmagadora das APIs vão até o #2.

**REST: HAL, Collection+JSON e Siren**

Hoje em dia usamos muito o JSON, antigamente XML era amplamente utilizado.

XML nos dava a capacidade de criar um documento e adicionar atributos a ele.

Com JSON não tem nenhuma padronização, então se a documentação não for muito boa, vai ficar bem dificil de trabalhar com a API.

Por conta disso que existem 3 padrões para criar uma API rest decente.

- HAL: Hypermedia Application Language
    - ![Exemplo HAL](https://i.imgur.com/uR6SJsy.png)
    - *_links.self* = O recurso que to acessando nesse momento. 
    - *_embedded* = Relacionamento com outros recursos *family* por exemplo.
- Collection+JSON

- Siren


**REST: HTTP *Method* Negotiation**

O HTTP possui outro método/verbo: **OPTIONS**. Que permite sabermos quais métodos HTTP estão disponíveis em um endpoint específico.

Requisição:

```
OPTIONS /api/product HTTP/1.1
HOST: meuserver.com.br
``` 

Exemplo de resposta:

```
HTTP/1.1 200 OK
Allow: GET, POST
``` 

Caso envie a requisição com um método HTTP que não está listado acima (PUT por exemplo), a resposta seria:

```
HTTP/1.1 405 Not Allowed
Allow: GET, POST
``` 

**REST: HTTP *Content* Negotiation**

**Accept negotiation:** Quando o cliente envia a requisição, ele pode pedir o tipo do retorno com o header **Accept:**

Requisição do cliente:

```
GET /product
Accept: application/json
```

Se o servidor não dar suporte a resposta em JSON e está bem configurado, deverá responder:

```
HTTP/1.1 406 Not Acceptable
```


**Content-Type negotiation:** É para dizer pro servidor que você ta postando um payload em um determinado formato. JSON por exemplo.

```
POST /product HTTP/1.1
Accept: application/json <--- To dizendo que quero resposta em JSON
Content-Type: application/json <-- To dizendo que o meu payload abaixo é no formato JSON

{
    "name":"produto 1"
}
```

Se o servidor não suportar processar inputs no formato JSON, vai retornar:

```
HTTP/1.1 415 Unsuported Media Type
```