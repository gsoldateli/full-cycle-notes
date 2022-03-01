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

