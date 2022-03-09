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



