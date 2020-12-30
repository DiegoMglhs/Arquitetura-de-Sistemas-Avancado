# Arquitetura-de-Sistemas-Avancado
# Conceito de Integração de Sistemas em Mensageria

## prós e contras de uma arquiterua em mensageria?
#### Prós
-  Desacoplamento
-  Facil Pulg & Play
-  Comunicação Assincrona
-  Simples Escalabilidade
-  Broadcasting
-  Permite Event Source

#### Contras
-  single point of failure 
-  Dificil monitoramento


## Gerenciamento de Erros
- [ ] Dead letter queue (Filas de re-tentativas)
- [ ] Monitoramento entre serviços
- [ ] Rastreamento de fluxo
 
 ### Como fazer o rastreamento de fluxo
 -  guardar os logs de serviço em local centralizado
 -  ferramentas podem ajudar como ELK Stack da Elastic, na qual como consegue consumir esses logs do serviço e consiga guardar de forma indexada e armazerar em um só lugar
 -  Gerar um Tack ID de cada operação com seus metadata

# Arquitetura de dados não estruturados e business intelligence

## Business Intelligence em Modelos de Dados

#### BI - Business Intelligence
- [ ] O BI é composto basicamente por:
-  Ferramentas,
-  Infraestrutura,
-  Profissionais(corpo técnico),
-  ![#f03c15]Dados

###### De onde vem os dados da BI?
-  Vem inicialmente de serviços SGDB
-  Podem ser complementados por informações externas por exemplo ***Dados gerenciais da propria empresa***
-  Pesquisa de mercado
-  Indicadores de mercado(alta ou queda de bolsa)

###### BI-Solution
**Uma solução basica em BI deve ter ao menos**
-  Infraestrutura
-  Gerenciamento de dados
-  Analytics (ferramenta de analize ou explosição dos dados)
-  Compartilhamento
-  Ferramentas gerais como:
    -  controle de acesso
    -  redundancia a falha
    -  aspectos de inteligencia artificial

## Aprenda sobre os conceitos de Data Warehouse

### Data Warehouse
###### OLTP x OLAP
- [ ] On-Line Transaction Processing
    - transções online
    - incersão de novo cliente
    - incersão de nova venda
    - atualização de preço do produto

- [ ] On-Line Analytical Processing
    - Analise dos dados
    - normalmente não devem ser alterados (após serem consolidados)

###### Os relatórios podem gerar cubos de visões
- Divisões em:
    - tempo
    - geografia
    - membros (itens)
***Estrurua já consolidade desses dados são chamadas de OLAP ou DW (Data Warehouse)

## O que é Big Data e dados não estruturados

### O que é BigData?
***São Formatos diversos de informação onde precisamos retirar informações***

###### Dados Estruturados
Para inserir/deletar uma nova coluna, precisa alterar a estrutura da tabela para receber essa nova coluna

###### Dados Semi-estruturados
**NoSQL = Not Only SQL**
*Se comportam como BD relacionais, mas te dá mais flexibilidade para inserir dados sem uma regra muito específica*

###### Dados Não Estruturados
- Apenas uma grande coleção de várias informações estruturadas e semi estruturadas
- Precisa de ferramentas para gerir essas informações, como:
    - hadoop
    - HDFS
    - Apache Spark
    - Apache Strom
    - Google BigQuery
    - Presto

## Data Lake vs Big Data
##### Nada mais é que um "bigData"
     mais reservado
     mais corporativo 
     mais tratratado
**Precisa de um Data Curation, um pré trabalho nesses dados para eles "entrarem no lago de informações"**

### Pratica no MongoDB
*utiliza Json*
***Exemplos:***
- use loja 
    -(cria um db loja)
- db.produtos.insert({codigo:"01", descricao: "caneta"}) 
    - (insere uma linha na tabela produtos)
db.produtos.find() 
    - (uma função, correspondente ao select)
    
# Fundamentos de arquitetura de aplicações em nuvem

#### Arquitetura em nuvem e sua evolução
##### Cloud Computing
- Gerenciamento de hardware/sofware
- Provedores de servidor e armazenamento
- Pague o que consumir
-  Iaas / Pass / Baas 

###### IaaS
**Infrastructure as a Service**

###### PaaS
**Plataform as a Service**

###### BaaS
**Backend as a Service ou Mobile Backend as a Service**

- Toda complexidade do back End entregue como um serviço
- Por exemplo o Firebase oferece o servico do backend lidando com:
    - autencicação
    - permições
    - dados
    - entre outros
- Assim o desenvolvedor front end só precisa conectar com a API de uma estrutura dessa como no exemplo a API do Firebase.

### Entenda sobre disponibilidade de aplicações

#### Disponibilidade
- [ ] Infraestrutura - Benefício
- IaaS - Hardware e Inetnet
- PaaS - Auto sacele on the go
- BaaS - não há backend service

***Garantir disponibilidade e orquestração de containers***
- Kubernets (K8S)
- Multiplos nodos
    - nº mínimo de instancias são 3
- Load balancer

### Aprenda a executar serviços com Serveless
*aumenta o complexidade do serviço*
- *Significa sem servidor*
- Sem serviço "rodando"
- Sem down time
Um evento dispara um serviço meu, isso é chamado de **lambda functions**
- Custo acaba sendo maior, por pagar pela abstração
- numero maior de lambdas (são pequenas para não ser um microserviço)
- max de 15 minutos

# Desenvolvimento e operação de software integrado

### O que é DevOps?
*como era? As areas eram separadas*
- Development
- Quality Assyrance (QA)
- IT Operations

**DevOps**
*Integra os times antes separados*

"**DevOps** é um termo criado para definir o conjunto de praticas que itegram e automatizam os processos entre as equipes de desenvolvimento, operações e de apoio(Como QA) para a produção rapida e confiavel de sfotware"

#### Franework CALMS
- Culture
- Automation
- Lean
- Meansurement
- Sharing

##### Os Três Caminhos

- **Flow**
    - A otimização do fluxo, visa eliminar desperdícios, gargalos no processo, tranferência de responsabilidades e tempos de espera
- **FeedBack**
    - Ciclos rápidos de feedback visam resolver problemas o quanto antes
    - O monitoramento constrante é a chave, ajudando a gerar informações relevantes.
- **Learning**
    - O aprendizado contínuo visa gerar conhecimento através da experimentação.
    - Hipóteses são melhores do que uma certeza imediata.
    - A chave é o trabalho dinâmico, com times realiazndo experimentos em seu trabalho diário para gerar novas melhorias
    - Elimine a cultura da culpa

### Continuous Integration

### Continuous Inspection
- *principais do mercado*
    - sonarQube
    - CODE Climate
    - Codacy
###### Verifica a complexidade do código

###### Vulnerabilidades / Code Smell

###### Padronização e Estilo

###### Débito Ténico

