# Fundamentos de Arquitetura de Software

# Introdução a arquitetura de software

### O que é arquitetura?

É a organização de um sistema, contemplando seus componentes, os relacionamentos entre estes e o ambiente, e os princípios que governam seu projeto e evolução. ISO 42010:2011

### Pilares da Arquitetura de Software

- Organização de um sistema
- Componentização
- Relacionamento entre sistemas
- Governança
- Ambiente
- Projeto
- Projeção
- Cultura

### Frameworks

Ferramentas e métodos que nos ajudam a focar essencialmente no objetivo final. Ajudam a delimitar um padrão de trabalho.

### Frameworks conhecidos

- The TOGAF Standard

É um framework conceitual que ajuda nos processos de arquitetura. Fornece conceitos e nomenclaturas, visão geral dos principais tipos de arquiteturas:

- Negócio
- Sistemas de Informação
- Tecnologia
- Planos de migração

- IEEE 42010:2011

Framework mais simplicado que o TOGAF, lançado em 2011 pela ISO, formaliza os fundamentos da área de arquitetura de software de modo mais direto.

### Momentos da arquitetura na História

- Tradicional
    
    Metodologia de desenvolvimento: **Cascata/Waterfall**
    
    Tipos de aplicações: **Monolitico**
    
    Infraestrutura: **on-premise**
    
- Momento Atual
    
    Metodologia de desenvolvimento: **Agile**
    
    Tipo de aplicação: **Multi-tier architecture**
    
    Infraestrutura: **Virtualização**
    
- Momento Emergente
    
    Cultura: **DevOps e Full Cycle**
    
    Tipos de aplicações: **baseadas em microserviços**
    
    Infraestrutura: **Containers**
    
- Momento Futuro
    
    NoOps: **Nuvem**
    
    Tipo de aplicação: serverless
    
    Infraestrutura: **Public Cloud**
    

### Introdução a escalabilidade e sistemas monolíticos

- Sistemas monolíticos
    - Contras
        - Alto acoplamentos
        - Tudo dentro do mesmo sistema
        - Deploy completo a cada entrega
        - Normalmente usa uma única tecnologia
        - Um problema afeta todo o sistema
        - Maior complexidade para times
    - Prós
        - **Atende a maioria dos casos**
        - **Menor complexidade**
        

### Escalando Software

- Escala vertical

Conforme o aumento do uso eu aumento o poder de processamento (recurso computacional)

- Escala horizontal

Conforme o aumento do uso  eu adiciono novas instâncias (máquinas) da aplicação.

### Detalhes sobre a arquitetura da aplicação

- Disco efêmero
- Servidor de aplicação x Servidor de Assets
- Cache centralizado
- Sessões centralizadas
- Upload / Gravação de arquivos

Tudo pode ser distribuído e criado facilmente.

### Escala horizontal na aplicação monolitica

- Ter imagens / containers
- Ser facilmente reconstruídas
- Ter suas responsabilidades
- São facilmente escaláveis

### Quando aplicações monolíticas deixam de valer a pena?

- Times grandes
- Necessidade de escalar todo o sistema pelo fato de uma funcionalidade específica sobrecarregada
- Risco de deploy completo começa a se elevar
- Necessidade de utilizar tecnologias diferentes

## Introdução aos microsserviços

### O que é um serviço?

- Disponibiliza informação
- Realiza transações
- Resolve um problema de negócios
- Independe de tecnologia ou produto
- Pode estabelecer comunicação com diversos clientes

### SOA → Service Oriented Architecture

- Serviços maiores baseados em funcionalidades
- Necessidade de ESB
- Single point of failure
- Compartilham banco de dados, comumente

### Arquiteturas baseadas em Microserviços

- Serviços pequenos com poucas responsabilidades
- Maior tolerância a falhas
- Totalmente independente
- Cada serviço possui seu próprio banco de dados
- Comunicação síncrona ou assíncrona

### Microserviços não são para todas situações

- Arquitetura complexa
- Custo mais elevado
- Necessidade de equipe maior
- Sistema precisa ser grande para justificar
- Gera problemas que normalmente você não tinha antes
- Monitoramento complexo

### Microserviços - Principais caracteristícas

Foram definidos, por Martin Fowler, 9 caracteristícas principais dos microsserviços. São elas:

1. Componentização via serviços

**Componente é uma unidade de software independente que pode ser substituída ou atualizada.**

Desvantagens

- Chamados externos são mais custosos do que chamadas locais
- Cruzamento entre componentes pode ser complexo
- Transações entre serviços são grandes desafios
- Mudanças bruscas em regras de negócios podem afetar diversos serviços tornando o processo difícil de ser refeito

 

1. Organização em torno do negócio

**Um projeto é baseado em um ou mais produtos que trabalham em diferentes contextos**

- Time de desenvolvedores por produto
- Muitas empresas tratam times com Squads
- Squads são multidisciplinares
- Cada produto pode ter um ou mais serviços envolvidos

1. Smart Endpoints e Dumb Pipes
- Exposição de APIs
- Comunicação entre serviços
- Comunicação síncrona e assíncrona
- Utilização de sistemas de mensageria
- Garantia de que um serviço foi executado baseado na execução das filas

1. Governança descentralizada
- Ferramentas certas para trabalho certo. Tecnologia definida baseada na necessidade do produto
- Diferentes padrões entre squads

1. Automação e infraestrutura
- Uso de Cloud Computing
- Testes Automatizados
- C/D
- C/I
- Load balance / Autoscaling

1. Desenhado para falhar
- Tolerância a falha
- Serviços precisam de fallback
- Logging
- Monitoramento em tempo real
- Alarmes

1. Design evolutivo
- Produtos podem ser extintos ou evoluir
- Gerenciamento de versões
- Replacement and upgradeability

### API Gateway

Recebe todos os chamados de APIs dos clientes e então as roteia para os microserviços correspondentes.

### Service Discovery

- Responsábel por prover mecanismos de identificação dos serviços disponíveis e suas instâncias.

### Client Side e Server Side

Os servi;os são registrados no Service Registry e este informa qual está disponível. O cliente busca no Service Registry.

Também pode ser colocado um load balance entre o client e o service registry.

- Ferramentas populares
    - Netflix Eureka
    - Consul
    - Etcd
    - Zookeeper

### Comunicação entre microserviços

- Dupla latência

O sistema pode se tornar lento de acordo com os serviços que executarão para que se retorne uma solicitação, causando dupla latência.

- Há abordagens que não utilizam filas em requisições síncronas

### Backend for frontend

- É o backend que se adapta ao front-end que estiver consumindo os dados
- Não há limites para trabalhar com BFF.