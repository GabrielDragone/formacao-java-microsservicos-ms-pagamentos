# Formação Aprofunde em Java com arquitetura de Microsserviços, Spring e RabbitMQ:
Curso alura: https://cursos.alura.com.br/formacao-java-microsservicos

Projeto e anotações referentes à formação "Aprofunde em Java com arquitetura de Microsserviços, Spring e RabbitMQ".

---
### 1. Criando um microsserviço:
#### Podcast: Case Banco PAN: Cloud e Microsserviços Hipster Ponto Tech #306:
* Monolito: 
  * Crises constantes, pouca visibilidade, sem monitoração, dificil "instalar", tempo de desenvolvimento mto grande. Deploy demorado numa estrutura gigante. Dificil escalar. É dificil lançar coisas novas.
* Microsserviços:
  * Mais fácil escalar, fazer manutenção, deploys mais rápidos.
* O que fazer para migrar?
  * Identificar quais módulos existem para separá-los.
  * Verificar onde precisa de mais escalabilidade, estabilidade e performance pra priorizar.
  * Serviços mais críticos.
* Kaizen: Processo de melhoria continua.
#### Curso: Microsserviços na prática: entendendo a tomada de decisões:
#### 01. Boas vindas à realidade:
1. Apresentação:
   * Exemplos reais. Análise de tomadas de decições. Comunicações entre microserviços. Trafeas de plano de fundo. Infra. GitHub Actions.
   * Ms de marketing, ms de pagamento, ms academico.
   * Comunicações assíncronas.
2. Conhecendo o projeto:
   * Tela de preenchimento de dados é um ms.
   * Tela de pagamento é outro ms.
3. Conhecendo cada componente:
   * ![img.png](img.png)
   * Repare que em nenhum momento foi feita comunicação direta, estamos usando comunicação assíncrona.
4. Componentes de linguagens:
   * Todos os componentes de um mesmo serviço precisam usar a mesma linguagem de programação?
     * Não, porém é aconselhável, pois normalmente é apenas uma equipe que será responsável por todo o serviço, dessa forma, utilizando apenas uma linguagem pode facilitar a manutenção da eqioé e contratação de novos colaboradores.
5. Subindo o projeto:
   * Clonar o repositório https://github.com/CViniciusSDias/alura-ms.
   * Rodar comando git clone --recurse-submodules --remote-submodules https://github.com/CViniciusSDias/alura-ms.git
     * Clona repositório central e cada um dos projetos dos submodulos.
   * Rodar docker-compose up --build.
   * Acessar localhost:4200
     * Ao criar o usuario, os ms se comunicam via RabbitMq, envia email.
7. Só um comando:
   * Para termos nosso projeto em pé, bastou utilizartmos o docker-compose.
* OBS: Não continuei pq não gostei a abordagem de um curso de Java e Spring apresentar não ter o foco nessas linguagens.
#### Curso: Microsserviços na prática: implementando com Java e Spring:
* https://cursos.alura.com.br/course/microsservicos-implementando-java-spring
1. Apresentação:
   * Criação de 2 MS.
   * Utilização de Migrations.
   * Service Discovery pros ms se registrarem nele.
   * Balanceamento de carga.
   * API Gateway pra centralizar as requisições.
   * Comunicação síncrona.
   * Cirbuit Breaker.
   * Fallback.
   * ![img_1.png](img_1.png)
2. Projeto e conceitos:
   * Objetivos e necessidade:
     * Facilidade de mudança/manutenção.
     * Times menores e autonomos.
     * Reuso.
     * Diversidade tecnológica e experimentação.
     * Maior isolamento de falhas. Caso falhe, não afeta as demais.
     * Escalabilidade independente e flexível.
   * Funcionalidades do monolito migrado:
   * ![img_2.png](img_2.png)
   * A ideia é aos poucos remover as partes mais críticas. Aqui isolaremos Pagamento e Pedido.
3. Para saber mais: Arquitetura de Microsserviços:
   * O que são microsserviços?
     * https://cursos.alura.com.br/extra/alura-mais/o-que-sao-microsservicos--c699
     * Monolitos:
       * Mais fáceis de construir, porém conforme o sistema vai crescendo, vão ocorrendo:
         * Demoras no deploy
         * Falhas podem derrubar todo o sistema.
         * Apenas 1 tecnologia para o projeto.
     * Microsserviços:
       * Cada parte do nosso sistema é um serviço independente.
         * Tecnologias independentes.
         * Falha em 1 serviço é isolada.
         * Deploys menores e mais rápidos.
         * Equipes menores e autonomos.
       * Desvantagens:
         * Maior complexidade de desenvolvimento e infra.
         * Debug mais complexo.
         * Comunicação entre os serviços deve ser bem pensada.
         * Diversas tecnologias pode ser um problema.
         * Monitoramento é crucial e mais complexo.
     * Normalmente, quando uma empresa está começando, ela ópta por um sistema monolitico, pq é mais rápido e simples de ser feito.
     * Ai sim, separamos por módulo e vamos dividindo em ms.
   * Tipos de Microservices:
     * https://cursos.alura.com.br/extra/alura-mais/tipos-de-microservices-c698
     * Mais comuns são:
       * Data service: Fornece acesso direto à determinada fonte de dados.
       * Business service: Aglomerado de data service. Não só expôe dados, mas tem regras dentro dele.
       * Translation service: Permite a entrada de dados do nosso sistema e envia pra um sistema externo.
       * Edge service: Permite expor um tipo de serviço pra cada cliente.
5. Preparando o ambiente:
   * https://cursos.alura.com.br/course/microsservicos-implementando-java-spring/task/107427
6. 
---
### 2. Deploy do microsservico na nuvem:
#### Curso: Microsserviços na prática: IaC com CDK e deploy na AWS:
#### Curso: Microsserviços na prática: mensageria com RabbitMQ: