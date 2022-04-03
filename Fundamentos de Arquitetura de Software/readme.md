# Comunicação

# Introdução

- Quando se trabalha com microserviços um dos pontos críticos é a comunicação.
- Deve-se utilizar mais de duas formas para comunicação, simultâneamente
- Na maioria das vezes não necessáriamente preciso obter a resposta de todas as requisições em tempo real
- Quanto maior a importância de tempo real em alguma solicitação maior a chance de gerar fragilidade no seu serviço.
- Comunicação síncrona → Em tempo real.
- Comunicação assíncrona → A resposta ocorre em um tempo indeterminado.

# REST

- REST significa Representational state of transfer
- Surgiu em 2000 por Roy Fielding em uma dissertação de doutorado
- Simplicidade
- Stateless
- Cacheável

# Níveis de maturidade

- Nível 1 - Utilização de resources
    - Utilização dos verbos http com padronização de recursos
- Nível 2 - Verbos HTTP
    - Garantir que estou utilizando o verbo correto para a operação que estou tentando realizar
- Nível 3 - HATEOAS → Hypermedia as the Engine of Application State
    - Sempre vai responder o endpoint, trazendo o que eu vou poder realizar com os dados do recurso que estou trabalhando
    - A API fica autoexplicável, trabalhando como hipermídias.

# REST: Uma boa API REST

- Utiliza URIs únicas para serviços e itens que expostos para esses serviços
- Utiliza todos os verbos HTTP para realizar as operações em seus recursos, incluindo caching
- Provê links relacionais para os recursos exemplificando o que pode ser feito

# REST: HAL, Collection+JSON e Siren

- Com JSON não existe padronização de como vou entregar os dados
- JSON não provê um padrão de hipermídia para realizar a linkagem
- HAL: Hypermidia Application Language
- Siren;

# REST: HTTP Method Negotiation

- HTTP possui o método OPTIONS, que nos permite informar quais métodos são permitidos ou não em determinado recurso.

# REST: Content Negotiation

- O processo de content negotiation é baseado na requisição que o client está fazendo para o server. Nesse caso ele solicita o que e como ele quer a resposta. O server então retornará ou não a informação no formato desejado.
- Através de um content type no header da request o servidor consegue verificar se ele irá conseguir processar a informação para retornar a informação desejada.

# Laminas API Tools

É um construtor de API criado para simplificar a criação, mantendo a usabilidade, facilidade de consumo e boa estrutura da API.

Independentemente da sua experiência em construção de APIs, com API Tools você pode construir APIs que serão utilizadas em aplicativos mobile, comunidades de desenvolvimento e qualquer outro modo de acesso de consunmo controlado nas suas aplicações.

O Laminas API Tools é utilizado para implementar APIs em PHP.

# GraphQL