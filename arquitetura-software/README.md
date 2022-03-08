# Arquitetura de software


## Fundamentos
### Tipos de arquitetura

- **Técnológica:**
    - Especialista em técnologias especificas de mercado.
    - Geração de valor baseado em especialidade.
    - Exemplos:
        - Arquiteto Elastic
        - SQL Server
        - Arquiteto Java
        - Oracle
        - SAP
        - Salesforce
- **Corporativa:**
    - Impacta estratégicamente a organização como um todo.
    - Avalição de custos
    - Avaliação de novas técnologias
    - Padronização de tecnologias
    - Planejamento de grandes implantações
        - Sistemas "core".
        - Migrações
- **Solução:**
    - Fica entre a área de negócios e software.
    - Transforma requisito de negócio em solução de software.
    - Desenhos arquiteturais de solução de um software para reproduzir como ele vai funcionar.
        - C4
        - UML
        - BPMN
    - Analisa impactos comerciais em relação a escolha tecnológica.
    - Pode participar do processo de venda / pré-venda.
    - Analisa os impactos dos custos para o negócio.

- **Software:** É a relação entre objetivos de negócio e suas restrições com os componentes a serem criados e suas responsabilidades visando a evolução do software.
    - É uma disciplina da engenharia de software.
    - Diretamente ligada ao processo de desenvolvimento de software.
    - Afeta diretamente a estrutura organizacional da empresa.
        - Formação dos times.
        - Estrutura dos componentes de software.
        - Organizações que desenvolvem sistemas de software tendem a reproduzir sistemas que são cópia da estrutura de comunicação dessas empresas. --- (Melvin Conway)
            - Exemplo:
                - Se o time tem 1 FE, 1 BE, a tendencia é que o BE seja uma API e o FE uma SPA.
                - Se o time só tem programador BE, a tendencia é que o FE seja renderizado server side.


### Papel do arquitet(o|a) de software

- Transforma um requisito de negócio em um padrões arquiteturais.
- Orquestra desenvolvedores e experts de domínio.
- Deve entender de maneira profunda conceitos e modelos arquiteturais.
- Auxilia nas tomadas de decisões em momentos de crise. 
- Reforça boas práticas de desenvolvimento.
- Code Reviews.
- Mesmo que nem todas empresas tenham uma vaga/cargo de arquiteto de software, programadores mais seniores/leads acabam realizando esse papel baseando-se em suas experiencias anteriores.


### Por que aprender arquitetura de software?

- Poder navegar de uma **visão** macro para micro dos softwares.
- Ter mais opções na hora de criar uma melhor solução em um determinado contexto.
- Pensar no longo prazo e sustentabilidade dos projetos.
    - Quanto melhor aquitetado, mais retorno financeiro o software vai dar ao longo prazo.
- Tomar melhores decisões sobre quais tecnologias usar sem ser influenciado por hypes de mercado.
- Exposição intensa a padrões de projetos, desenvolvimento e boas práticas.
- **GERAR VALOR**:
    - Ter mais clareza do impacto que o software tem em uma organização como um todo.
    - Você se torna extremamente valioso para empresas que tem problemas que podem ser resolvidos através de software.
    - Tem muito desenvolvedor que sai da empresa pois não vê o impacto que está gerando com seu trabalho, perde o senso de pertencimento.
- Tomar decisões com mais **SEGURANÇA**
    
### Arquitetura VS. Design de software.

Tema polêmico, para uns arquitetura significa um coisa, para outros outra. Mas no fim das contas o que importa é ter repertório de possibilidades para resolver os seus problemas. É sua responsabilidade o sentido que faz do que lhe é dito.

Abaixo seguem algumas definições de acordo com o ponto de vista do curso FullCycle.

- Arquitetura: Escopo global / alto nível / Mais macro.
    - Capaz de ver:
        - Componentização
        - Forma de comunicação
        - Abstrações / Padronizações dos sistemas.
    - Tem por objetivo garantir que qualidade, restrições de alto nível e os objetivos do negócio, sejam atendidos pelo sistema.
- Design: Escopo mais local, exemplo:
    - Como consigo deixar uma classe com menos responsabilidades?
    - Como consigo implantar um pattern para facilitar a resolução de um problema?
- Macete para diferenciar as duas:
    - Ao falarmos de arquitetura, automaticamente estaremos falando também de design.
    - Mas ao falarmos de design nem sempre estaremos falando de arquitetura.
        - Tudo que fizermos que seja invisível de fora do componente é design.

Exemplo chocante:
    - Clean architecture do uncle Bob fala mais de **design** do que arquitetura em si.


### Sutentabilidade no dia 0 (Zero).

- Desenvolver software é caro.
- Software resolve um problema, uma "dor".
- Software precisa se pagar ao longo do tempo.
- A relação entre a empresa e o software é viva.
    - Por isso o software precisa se manter sincronizado com o funcionamento da empresa.
    - Nessa relação, o software precisa então ser atualizado com um custo muito menor do que o retorno que ele ta gerando para a empresa.
    - É sucesso quando a empresa fala assim: Que legal, o software que eu tenho **resolveu meu problema e estou lucrando mais** agora.
    - Imagina o drama quando um software tem um problema tão grave de arquitetura, que os devs dizem que o sistema precisa ser refeito. Todo o custo inicial de desenvolvimento se perde, bem na hora que ia ficar bom.
- Software precisa acompanhar a evolução do negócio.
- Quanto mais tempo o software fica no ar, mais retorno ele gera.

### Pilares da arquitetura de Software

- Estruturação: Como tudo vai estar estruturado.
    - Fácil evolução, componentização para atender os objetivos do negócio.
- Componentização
- Relacionamento entre sistemas.
- Governança
    - Criar documentações claras de como o desenvolvimento funciona, exemplo:
        - Template de PRs
        - Linguagens utilizadas
        - Organização de classes
        - Etc...
    - Sem isso o sistema fica dependente demais de pessoas especificas e assim gerando problemas caso elas saiam da empresa.

### Requisitos Arquiteturais

- Performance
    - Exemplo:
        - As requisições não podem passar de 500ms.
        - Suportar um throughput de 50 transações por segundo.
- Armazenamento de dados
    - Exemplo:
        - Se um servidor ta na europa, os servidores de arquivos tem que estar na europa.
- Escalabilidade
    - Horizontalmente ou Verticalmente
    - Load balancer vai funcionar como?
- Segurança
    - Exemplo:
        - Se for um ecommerce, se tem transações de cartão de crédito, tem que ter certificações PCI.
        - Comunicação entre micro serviçoes tem que ser criptografada.
- Legal
    - Exemplo:
        - LGPD
- Auditoria
    - Exemplo:
        - Logs
            - Onde vão ficar armazenados?
            - Quanto tempo vão ficar armazenados?
- Marketing
    - Exemplo:
        - Como a aplicação vai trackear de onde vem cada acesso?
        - Verificar tipos de dispositivo.


Como levantar esses requisitos todos? Planilha e um monte de pergunta para as áreas da empresa.


## Características arquiteturais


Todo sistema possui de uma forma ou de outra essas caracteríticas arquiteturais.
- Operacionais
- Estruturais
- Cross-Cutting

Geralmente são requisitos não funcionais, ficam ao redor das regras de negócio.

Sugestão de livro: **Fundamentos de Arquitetura de software.**


### Características Operacionais

- Disponibilidade
    - Qual os níveis de SLA, SLO ?
- Recuperação de desastres?
    - Como vou fazer para recuperar quando meu sistema estiver fora do ar?
    - Como evitar que o mesmo problema aconteça novamente?
    - E se uma região da AWS cai?
    - O quanto to disposto a pagar para ter um servidor multi região?
- Performance
    - Latencia
    - Throughput: Capacidade de receber requisições.
        - Projetar um sistema de 50000 mil requisições por segundo é diferente de projetar um para 50 requisições por segundo.
- Recuperação (Backup)
    - Qual a última vez que testei o backup que testei?
    - Criar políticas para testar backup.
    - Salvar backups em redes diferentes.
- Confiabilidade e segurança: Sistemas de missão crítica.
    - Bruteforce para fazer login
    - Menino mau fazendo bot para registrar milhares de contas fake. Recaptcha serve?
    - Que que eu faço se algum bot começar a forçar um endpoint da minha aplicação?
- Robustes 
    - Ele ta numa estrutura robusta o suficiente para que ele possa escalar de precisar?
    - A cloud não é infinita.
    - Você tem servidores AWS na Virginia, dai ele cai, você tenta mandar para Virginia do norte, mas não tem quantidade o suficiente de IPs lá. Como faz?
- Escalabilidade
    - Verticalmente: Aumentar recursos do servidor.
    - Horizontalmente: Aumentar número de servidores.
        - Trabalhar de forma stateless.
        - Seguir os 12 fatores 


### Características Estruturais

Ligadas ao processo de desenvolvimento e como vou desenvolver a aplicação.

Buscar que o software funcione de uma maneira cada vez mais flexível.

- Configurável
    - Botar configuração com banco de dados
        - Variáveis de ambiente com a conexão.
    - Tenho que alterar o endereço do gateway de pagamento. E agora? Ta fácil para mudar?
    - To usando vários gateways de pagamento, se um falhar quero utilizar outra.  Tá fácil de trocar?
    - Como saber se ela é configurável?
        - Upa a aplicação em staging e produção, se tiver que mudar código fonte é pq ela não é configurável.
- Extensibilidade: Ela tem que poder crescer de forma que novas funcionalidades possam ser plugadas nela.
    - Imagina que tua aplicação usa gateway de pagamento X e dai teu chefe diz para usar gateway Y.
        - Se tu tiver que sair alterando pontos estruturais da aplicação para inserir uma nova gateway, provavelmente projetou errado a aplicação.
        - A aplicação não deve ficar refem de vendors.
            - Camadas anticorrupção.
    - Se ta dificil de adicionar novas features, módulos, tem que repensar como ta estruturada a aplicação.
- Fácil instalação
    - Padronização do ambiente.
        - Containers, docker etc...
    - Dependências
        - Meu app vai gerenciar os indices do elastic search ou vão ser criados manualmente?
        - Tópico do Kakfa, app cria ou crio manualmente?
        - RabbitMQ app cria fila por ela mesma?
- Reuso de componentes
    - Quando falamos de sistemas distribuidos, muitas vezes equipes diferentes implementam multiplas vezes as mesmas coisas, por exemplo validações. Será que não vale a pena ter uma equipe responsável por cuidar de bibliotecas que podem ser utilizadas pelos times?
- Internacionalização
    - Backend 
        - Já tem formas muito maduras de lidar com isso no lado do servidor.
        - Moedas? Qual a moeda base? Como vai funcionar políticas de preço? 

    - Frontend
        - No frontend você já tem um design de uma forma, ao trocar de linguagem, começa a quebrar toda a UI.
- Fácil manutenção
    - Não é simples.
    - Quanto mais senior, mais você percebe quão dificil é fazer uma solução complexa que você fez, fique simples.
    - Aprenda:
        - SOLID de verdade.
        - A pensar muito bem as camadas do seu sistema.
        - Como usar Adaptadores e Interfaces.
    - Atividades de manutenção
        - Correção de bugs
        - Adicionar novas features
        - Perguntas pra saber se tá okay
            - Tá fácil corrigir bugs?
            - Tá fácil implementar novas features?
            - Tem testes?
                - Não? não vai ter fácil manutenção.
- Portabilidade (diversos bancos de dados)
    - Tá fácil mudar banco de dados?
    - Sistemas de observalidade Elastic Search pra um DataDog ?
    - Vale a pena usar um Open Telemetry que serve de adapter pra várias dependencias de observalidade?
- Fácil suporte (logs, debugging)
    - No momento de operação da aplicação, tem que ser fácil de ver o que está acontecendo em produção.
    - Fazer benchmarks
    - Centralização de logs
    - Padrão de geração de logs.
    - Criar métricas.


### Características Cross-Cutting

Pontos que vão cruzar a aplicação de forma geral, no dia-dia temos que levar em consideração.

- Acessibilidade
    - Ter bem claro quem é o público que vai acessar a minha aplicação.
    - Tá fácil de pessoas com deficiencias acessarem a minha aplicação?
- Processo de retenção e recuperação de dados. (quanto tempo serão mantidos?)
    - Apache Kafka permite definir tempo de retenção de tópicos.
    - Se tem dados que não são mais utilizados diariamente, da pra compactar e colocar em um storage mais barato.
- Autenticação de Autorização
    - Provedor de identidades, eg:. Keycloack
        - Como outros serviços vão acesar ele?
    - API Gateway:
        - É um mecanismo que fica na borda da aplicação, nele da para criar políticas de autenticação, timeout, quantidade de requisições, etc...
        - Muitos sistemas não utilizam mais autenticação pois ela ocorre na API Gateway.
        - O sistema já entende que se a requisição está chegando, é porque o usuário já está logado.
- Legal
    - Quanto tempo os dados tem que estar mantidos?
    - Onde vão estar mantidos?
    - Tudo o que acontecer com a aplicação tem que estar em conformidade com o que a lei do país diz.
- Privacidade
    - Como consigo minimizar problemas em relação a dados de usuários vazarem.
    - Desenvolvedor gosta de testar com dados de produção.
        - Quer coisa mais simples pra vazar dados?
    - Muitas empresas separam dados sensíveis em outros bancos de dados.
- Segurança de ponta a ponta
    - Já começa a pensar na segurança da aplicação desde a borda. Bem antes do usuário cair no servidor.
        - Trabalhe com web firewall
            - Ajuda bastante com testes que o OWASP faz.
        - Crie regras e mecanismos que identifiquem robos.
    - Utilize ao máximo tudo que é padrão aberto.
        - Não inventa uma criptografia própria.
        - Não tente criar sua rotina de login.
    - Mantenha banco de dados em servidor separado.
    - Tenha backups em rede separada.
- Usabilidade
    - Usabilidade não é só no frontend.
    - Como está organizada a sua API?
    - Está trabalhando com padrões claros tipo Open API?
    - Tem contrato claros que posso disponibilizar para outras pessoas?
    - Como a API ta documentada? Tem README.md?
    - Quem é o cliente da minha aplicação? É outra aplicação? 
    - Como vou dar a melhor forma para essas pessoas / aplicações interagirem com a minha API ?


## Perforamance


### Perspectivas para arquitetar software de qualidade

- Performance
- Escalabilidade
- Resiliência: Planos B's para quando as coisas dão errado.


### Métricas para medir a performance.

- O que é performance?
    - É o desempenho que um software possui para completar um determinado workload.
        - São necessários dados para saber disso.
        - Você vai comparar a performance contra o próprio software, não contra o vizinho.
- Unidades de medida para avaliarmos a performance de um software:
    - Latência ou "Response time".
    - Throughput: Mostra o quanto de requisição o software pode aguentar.
- Ter um **software performatico** é **diferente de** ter um **software escalável**. 


Melhorando a performance do software:

- Diminuir latência.
    - Normalmente medida em milliseconds.
    - Se medida em segundos é porque a aplicação já ta lenta.
    - É afetada pelo tempo de processamento da aplicação, rede e chamadas externas.
- Aumentando o throughput.
    - Aumentar capacidade de lidar com mais quantidade de requisições
    - Diretamente ligado a latência.

### Checklist para aumento de performance

Principais razões para baixa performance

- Processamento ineficiente
- Recursos computacionais limitados
- Trabalhar de forma bloqueante
- Acesso serial aos recursos
    - Por exemplo fazer requisição no FE com setTimeout para um endpoint específico.

Principais formas para aumentar a eficiência

- Escala de capacidade computacional (CPU, Disco, Memória, Rede).
- Lógica por trás do software (Algoritimos, queries, overhead de frameworks).
- Concorrência e paralelismo.
    - Trabalhe com uma linguagem de programação que permita trabalhar com isso.
        - Em Go, por exemplo, para cada acesso em um webserver Go, uma thread é criada.
- Banco de dados (tipos de bancos, schema)
    - Será que ta modelado corretamente?
    - Será que to usando as melhores estratégias ?
    - Será que tem indice?
    - To dando explain nas minhas queries?
    - Tenho ferramenta de APM que mostra a query que ta matando o banco?
- Caching 

### Escala concorrência e paralelismo

![Escala vertical vs horizontal](https://i.imgur.com/GGTOcw3.png)

**Escala vertical:** Toda vez que aumentar a capacidade da aplicação, aumenta a capacidade computacional do servidor.
    - O limite é o hardware.
    - Todos os ovos numa cesta só, caiu servidor, caiu tudo.

Imagine um webserver que demora 50ms para responder uma requisição.

10ms --> 10ms --> 10ms -> 10ms = 40ms para responder as 4 requisições.

**Escala horizontal:** Toda vez que aumentar a capacidade da aplicação, aumenta o numero de servidores com load balancer na frente.

Imagine um webserver que demora 10ms para responder as mesmas 4 requisições.

```
Ele vai ter 4 threads:
--------
 - 10ms
 - 10ms
 - 10ms
 - 10ms
--------
10ms no total
```

**Qual a diferença entre concorrência e paralelismo?**

"**Concorrência** é sobre lidar com muitas coisas ao mesmo tempo. **Paralelismo** é fazer muitas coisas ao mesmo tempo." Rob Pike

O paralelismo é o motivo pelo qual NodeJS / Php Swool / Go são tão famosos.



### Caching

Guarda na memória coisas que já foram processadas antes.

- **Cache na borda === Edge computing:** O usuário nem bate na aplicação, ele é respondido direto por outro servidor que armazenou o cache.
    - Muito mais rápido.
    - Distribuido.
    - Custo baixo.
- Dados estáticos
    - Imagens
    - CSS
    - bundles js
- Páginas web
    - Estáticas
    - Dinamicas:
        - 1 - Processa (busca no banco etc..)
        - 2 - Salva output no cache
        - 3 - Faz tudo novamente em algum periodo de tempo.
- Funções internas
    - Evita processamento de algorítimos pesados.
    - Reduz acesso a banco de dados.
- Objetos
    - Objeto do Doctrine por exemplo.

Tipos de cache:

- **Exclusivo:** Local na máquina.
    - Baixa latência.
    - Duplicado entre nós.
    - Problemas relacionados a sessões.
- **Compartilhado:** Fica em um servidor centralizado. 
    - Maior latência.
    - Não há duplicação.
    - Sessões compartilhadas.
    - Banco de dados externo
        - MySQL
        - Redis
        - Memcache


### Caching VS. Edge Computing

**Edge computing**

Fornece serviços que podem processar dados do usuário sem bater no servidor da aplicação.

- Deixa os dados do usuário mais perto dele geograficamente.
- Cada vez mais em evidência.
- Hoje em dia a internet não vai mais funcionar se não existir Edge Computing.
- Imagina a netflix, imagina o trafego todo.
    - Se tiver um servidor central, derruba ele.
    - Isso derruba até a internet, inunda os backbones todos.
- Arquivos estáticos pode deixar na Edge sem nem pensar.
    - CSS
    - HTML
    - Imagens
    - JS
- CDN - Content Delivery Network.
    - Malha de servidores espalhados pelo mundo.
    - Todo conteúdo se replica entre os servidores.
    - Toda vez que alguém quiser acessar um conteúdo, acessa no servidor mais próximo.
- Cloudflare workers
    - Plataforma de Edge computing
    - Workers permitem que sejam feitos deploys de aplicações JS. Usando um minicontainer de V8.
- Vercel

**Exemplo de funcionamento Akamai:** 

Usuário do meu sistema requisita endpoint ---> AKAMAI ---> Baixa conteúdo do servidor --> Gera Midgrass --> Manda para os parceiros.

Eu pago uma taxa de transferência do servidor mais próximo do meu usuário.


## Escalabilidade

"É a capacidade de sistemas suportarem o aumento (ou redução) dos workloads incrementando (ou reduzindo) o custo em menor ou igual proporção." - Elemar.

### Escalabilidade VS Performance.

- Performance visa:
    - Reduzir latência
    - Aumentar throughput.
- Escalabilidade visa:
    - Possibilitar aumentar/diminuir o throughput adicionando / removendo capacidade computacional.


### Escalando software - Descentralização.

Para escalar um software descentralizadamente, você tem que ter alguns cuidados.

- Não armazenar estado no servidor da aplicação.
- Pensar que as máquinas são descartáveis. Elas podem ser criadas e derrubadas rapidamente.
- Disco tem que ser efêmero.
- Servidor de aplicação vs. Servidor de assets
- Cache centralizado em um servidor específico.
- Sessões centralizadas.
- Upload / Gravação de arquivos.


### Escala banco de dados

É um tema bem cabeludo.

Geralmente requer ajuda de um arquiteto tecnológico.

Como escalar?

- Aumentar recurso computacional.
- Distribuindo responsabilidades (escrita vs leitura).
- Shards de forma horizontal
- Não tem mágica, tem que entender os tipos de banco de dados para escolher a melhor opção para cada situação.
- Serverless 
    - Deixar o Cloud Provider se virar.
- Otimização de queries e índices.
    - Tenha sistema de APM = Application Performance Monitor.
    - Trabalhar com indices de forma correta.
    - APM nas queries.
    - Explain nas queries.
    - Utilizar pattern CQRS (Command Query Responsability Segregation) - Separar leitura / escrita.

### Proxy Reverso

Proxy em inglês = Procurador, alguém que fala em seu nome.

Proxy reverso é um servidor que fica na frente dos servidores web e encaminha solicitações do cliente (eg.: Browser) para esses estes.

![Proxy Reverso](https://i.imgur.com/Yncg1fE.png)

Soluções populares de Proxy Reverso

- Nginx
- HAProxy (HA = High Availability)
- Traefik

## Resiliencia

Conjunto de estratégias adotadas intencionalmente para **adaptação** de um sistema quando uma falha ocorre.

Ter estratégias de resiliencia nos possibilita minimizar o risco de perda de dados e transações importantes para o negócio.

### Quais as estratégias?

- Proteger e ser protegido
    - Hoje é muito comum trabalhar com microsserviços.
        - Proteger a nossa aplicação e a aplicação dos serviços.
        - Um sistema não pode ser egoísta ao ponto de realizar mais requisições em um sistema que está falhando.
    - Um sistema lento no ar é muitas vezes pior que um sistema lento no ar. (Dominio).

- Health Check
    - Verificar saúde do servidor que vai ser requisicionados.
    - Sem sinais vitais, não consigo saber a saúde.
    - Ter mecanismo que periodicamente roda health check.
        - Se estiver muito pesado, outros serviços mandam menos requisições. (Self-healing)
    - Health check de qualidade
        - Média do tempo das últimas requisições
        - Tempo de consulta no banco.
        - Quais métricas realmente representam a qualidade de vida do sistema?


### Rate Limiting

Protege o sistema baseado no que ele foi projetado para suportar. X requisições por ms/min/hora.

Barra requisições até atingir limite.


- Tem que saber o limite que o sistema aguenta.
- Preferencia programa por tipo de cliente.
    - Tem sistemas que tem mais preferencia que outros para utilizar um servidor.


### Circuit Breaker

Protege o sistema fazendo com que as requisições feitas para ele sejam negadas, eg:. erro 500.

- Sua casa tem um disjuntor que ao dar um sobrecarga, o disjuntor abreo circuito.

- **Circuito Fechado** = Sistema falando com outro sistema.
- Quando essa comunicação fica lenta, abre o circuito.
- **Circuito aberto** = Requisições não chegam ao sistema. Erro instantaneo  no client.
- O beneficio disso é que a requisição não fica dependurada no cliente.

- **Meio aberto** : Permite uma quantidade limitada de requisições para ver se o sistema tem condições de voltar ao ar integralmente.

- Pode ser implementado diretamente no código da aplicação.
    - Existem também recursos mais modernos, Service mesh por exemplo. Que aplica circuit-breaker direto na rede.

### API Gateway

Centraliza todas as requisições aplicando regras / políticas para para aceitar ou recusar requisições.

Respeitando as necessidades individuais de cada sistema.

- Garante que requisições "inapropriads" cheguem até o sistema. Ex: Usuário não autenticado.
- Tipos de API gateway
    - Kong
    - Kubernetes
- Implmenta políticas de
    - Rate Limiting
    - Health Check
    - Etc...

### Service Mesh

Malha de serviços.

- Cruamente falando, ela controla tráfego da rede.
- Permite colocar proxies do lado de cada sistema nosso.
    - Quando sistema A quer falar com sistema B, ele acaba mandando transparente a requisição pro "sidecar" que é o proxy do serviço.
        - Assim da pra saber tudo que ta passando pra rede, quem passa informação para quem, quando, quanto.
- Ajuda a entender o comportamento da minha rede.
- Evita implementações de proteção pelo próprio sistema. possibilitando trabalhar de forma automatica com:
    - Circuit breaker
    - Rate limit
    - Retry
    - Timeout
    - Fault Injection
    - Etc...
- Quem é que vai saber de verdade os valores das configurações? Não é o programador em tempo de desenvolvimento.
- mTLS - Criptografa as requisições.
    - Quando um sistema quer falar com o outro, criptografa a conexão.

### Comunicação Assíncrona

- Evita perda de dados
- Com menos poder computacional o serviço consegue dar conta de mais requisições.
- Imagina um sistema de pagamento que ta rebootando e quando alguém ta pagando, o sistema cai e da uma mensagem: Erro, o sistema está fora, tente pagar depois.
    - O pagamento se perdeu.
- Não há perda de dados no envio de uma transação se o server estiver fora.
- Servidor, mesmo fora do ar, consegue processar uma requisição.
- Os dados são enviados para o message broker/sistema de stram, eg:. Kafka.
- Entenda com profundidade seu message broker.


### Garantias de entrega com Retry

Tendo o sistema de filas em mente, as garantias de retry são responsáveis por definir a estratégia de quando uma nova tentativa será feita.

**Linear (Sem Backoff)**

![Linear](https://i.imgur.com/K6APc6o.png)

Tenta linearmente a cada X segundos, ela não funciona, pois se 10 sistemas fizerem requisição para um sistema especifico, e ele arregar, todas irão fazer uma nova requisição daqui a X segundos ao mesmo tempo novamente.

**Exponential Backoff**

![Exponential](https://i.imgur.com/pDF26h9.png)

A linha rosa = sem nenhum backoff, atente para quantidade de chamadas até conseguir responder.

A linha azul é Exponential Backoff, que calcula a próxima tentativa exponencialmente assim:

> 1s, 2s, 4s, 16s, 32s, 64s, 128s, 256s... n²

Mesmo que seja melhor que linear backoff, ainda não é uma melhora expressiva.

**Exponential Backoff - Jitter**

![Exponential w Jitter](https://i.imgur.com/7tMc3TL.png)

Para cada chamada, é rodado um pequeno algorítimo para gerar um pequeno ruído que randomiza a próxima chamada com um modificador de tempo.

1s, 2.3s, 4.1s, 16.05s

### Garantias de entrega com Kafka / Message Broker


![Message broker](https://i.imgur.com/vo57JAd.png)

Como eu tenho a certeza de que a informação que to mandando está chegando mesmo no message broker?

Níveis de garantia:

- None / Fire & Forget (Ack 0)
    - Alta velocidade podendo perder as mensagens.
    - Imagina as posições do Uber, vai fazer diferença perder algumas? Provavelmente não, então fire & forget é uma boa pois ganha na velocidade.
- Leader (Ack 1)
    - Moderado, apenas o lider confirma.
    - Imagina que ta mandando 1 real para o broker, o minimo que tu vai querer saber é se alguém lá recebeu né? Dai o lider da o retorno dizendo que recebeu.
- ALL (Ack - 1 )
    - Lento e seguro, todos brokers recebem a mensagem.
    - É útil quando você manda uma mensagem **Ack 1** e por algum motivo o leader cai depois de ter dito que recebeu... Dai você fica pensando que ta tudo certo, mas não está. Com **Ack-1** replica a mensagem entre os brokers.
    - Antes do leader avisar que recebeu, ele avisa que ele recebeu e também os demais brokers Followers.

Moral da história: Conheça o broker de mensagens que você está trabalhando bem o suficiente para saber os níveis de garantia que ele pode lhe proporcionar.
