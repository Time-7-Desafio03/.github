# Projeto de micros serviços para tomada de decisões - README

<img width="30%"  src="https://github.com/Time-7-Desafio03/.github/blob/main/profile/CompassLogo.svg"/>

Este é o readme de descrição do projeto de tomada de decisões, desenvolvido como parte do estágio na Compass UOL. Este projeto utiliza um conjunto de micro serviços, incluindo gestão de funcionários, gestão de propostas e gestão de resultados, integrados via um gateway. A comunicação entre serviços é realizada através do Open Feign e mensageria via Kafka.

## Desenvolvedores

- Elias Mathias Sand: [elias.sand.pb@compasso.com.br](mailto:elias.sand.pb@compasso.com.br)
- Joao Pedro Golenia: [joao.golenia.pb@compasso.com.br](mailto:joao.golenia.pb@compasso.com.br)
- Jonas Roberto Leandro: [jonas.leandro.pb@compasso.com.br](mailto:jonas.leandro.pb@compasso.com.br)
- Lucas Henrique Teixeira Ribeiro [lucas.teixeira.pb@compasso.com.br](mailto:lucas.teixeira.pb@compasso.com.br)

## Instrutores (PO)

- **Rafael Henrique Menegon:** [@devrafamenegon](https://github.com/devrafamenegon)
- **Edmar Miller Gabriel:** [edmarmiller@hotmail.com](mailto:edmarmiller@hotmail.com)
- **Cleiton Fiatkoski Balansin:** [cleiton.balansin@compasso.com.br](mailto:cleiton.balansin@compasso.com.br)
- **Mateus de Oliveira e Silveira:** [@mosilveira](https://github.com/mosilveira)
- **João Caetano Nicoli Tavares:** [jaonicoli@gmail.com](mailto:jaonicoli@gmail.com)
- **Rafael Luz de Queiroz**: [rafinhalq@gmail.com](mailto:rafinhalq@gmail.com)
- **Lucas Magno Peixoto Lima**: [lucasmagno695@gmail.com](mailto:lucasmagno695@gmail.com)
- **Manoel Rosa**: [guiguel@gmail.com](mailto:guiguel@gmail.com)

## História

- Imagine que você é um desenvolvedor encarregado de criar um sistema de backend para gerenciar processos de tomada de decisões em uma empresa. Neste sistema, as equipes da empresa terão a oportunidade de propor e votar em diversas propostas para melhorias internas.

## Período

- Período de desenvolvimento: 04/06/2024 até 11/06/2024 às 12:30;

## Itens Obrigatórios

• Utilize Java e Spring Boot com Maven nas mesmas versões dos desafios anteriores;
• Use o banco de dados H2 para a entrega;
• Use API GATEWAY como ponto de entrada;
• Crie um ms para cadastro de funcionários;
• Crie um ms para cadastro de propostas;
• Crie um ms para armazenar os resultados e que seja consumidor para receber os dados finais da votação e que forneça uma API Rest para consulta desses resultados;
• Os micros serviços devem possuir o Spring Actuator em funcionamento;
• Descreva um README com todos os passos para execução de maneira simples para que mesmo um desenvolvedor com menos experiência consiga executar.


## Prazo

- O envio do repositório do desafio deve ser enviado até às 12hrs do dia 13/05.

## Requisitos

### Funcionalidades

1. Cadastro e edição de funcionários;
2. Registrar uma nova proposta de melhoria;
3. Iniciar uma sessão de votação para uma proposta (a sessão de votação deve permanecer aberta por um tempo determinado na chamada de abertura ou por padrão 1 minuto);
4. Receber votos dos funcionários nas propostas (os votos são apenas 'Aprovar' ou 'Rejeitar'). Cada funcionário deve ser identificado por um ID único e pode votar apenas uma vez em cada proposta.
5. Contabilizar os votos e fornecer o resultado da votação para a proposta.

*É crucial que as propostas e os votos sejam persistidos e não sejam perdidos com o reinício da aplicação.*

### Funcionalidades Adicionais

#### 1 - Mensageria e Filas

• O resultado da votação precisa ser informado ao restante da empresa, preferencialmente através de mensagens.
• Quando a sessão de votação for encerrada, envie uma mensagem com o resultado da votação.

#### 2 - Versionamento da API

• Implementação de mais atributos para armazenar dados (telefone, endereço…);
• Autenticação JWT;
• Ter mais de uma replica na configuração do Kafka;
• endpoint getall e exibição por paginação;
• Data e hora do voto;
• Integração com a AWS.

### Critérios a serem avaliados

• Simplicidade no design da solução, evitando o excesso de complexidade.
• Organização do código.
• Arquitetura do projeto.
• Boas práticas de programação, como manutenibilidade e legibilidade.
• Tratamento de erros e exceções.
• Explicação breve das escolhas feitas durante o desenvolvimento da solução.
• Testes unitários e integrados.
• Uso de testes automatizados e ferramentas de qualidade.
• Limpeza do código.
• Documentação do código e da API.
• Logs da aplicação.
• Mensagens e organização dos commits.

*Entregas em Docker são sempre bem-vindas*

Dicas:
• Realize testes rigorosos em sua solução para evitar bugs.
• Não inicie o teste sem resolver todas as dúvidas.
• Esteja ciente de que executaremos a aplicação para testá-la, portanto, forneça instruções claras para sua execução, incluindo qualquer dependência externa necessária.

## Instalação

Cria uma pasta com o nome de sua preferência entra nele e executa o CMD dentro desse arquivo

```CMD
# Primeiro clona esse repositório
$ git clone https://github.com/Time-7-Desafio03/propostas.git

# Depois entra no repositório
$ cd propostas

# Mover o arquivo docker-compose.yml para a pasta geral
$ move docker-compose.yml ../

# Volta para a pasta geral
$ cd ..

# Instalação do Kafka
Obs. Deve ter o docker desktop instalado no computador
$ docker compose up

# Clone dos outros repositórios 
$ git clone https://github.com/Time-7-Desafio03/eureka-server.git
$ git clone https://github.com/Time-7-Desafio03/funcionarios.git
$ git clone https://github.com/Time-7-Desafio03/resultados.git
$ git clone https://github.com/Time-7-Desafio03/cloud-gateway.git
```
### Etapas de Inicialização
Obs. O docker desktop deve estar com os containers do kafka em execução, basta executar o container com o nome da pasta criada;

1. eureka-server;
2. microsserviços funcionarios, propostas e resultados;
3. cloud-gateway.

E pronto, o projeto já está em funcionamento

## Utilização

*Obs. Para acessos com o Swagger, Actuator e H2 é necessário utilizar a porta aleatória gerada no Eureka Server!*

• Endereço para acesso do Eureka Server: http://localhost:8761;
• Endereço para acesso do Actuator: http://localhost:{porta}/actuator;
• Endereço para acesso do Swagger: http://localhost:{porta}/swagger-ui.html;
• Endereço para acesso do Kafdrop: http://localhost:19000.

**H2 API Funcionários**
- Endereço: http://localhost:{porta}/h2-funcionarios;
- JDBC URL: jdbc:h2:file:./funcionarios;
- User Name: root;
- Password: 1234;

**H2 API Propostas**
- Endereço: http://localhost:{porta}/h2-propostas;
- JDBC URL: jdbc:h2:file:./propostas;
- User Name: root;
- Password: 1234;

**H2 API Resultados**
- Endereço: http://localhost:{porta}/h2-resultados;
- JDBC URL: jdbc:h2:file:./resultados;
- User Name: root;
- Password: 1234;

### Endpoints

#### Funcionários Endpoints


|       Rota           |    Método    |                   Descrição                    |                                                                         
|   ---------------     | :----------: |  ----------------------------------------------  |                                                                           
|  `http://localhost:8080/api/v1/funcionarios`            |    POST      |  Cadastrar um funcionário                                | 
|  `http://localhost:8080/api/v1/funcionarios/cpf/{cpf}`            |    GET       |  Buscar funcionário por CPF                             |   
|  `http://localhost:8080/api/v1/funcionarios/inativar/{cpf}`        |    PATCH       |  Inativar funcionário por CPF                       |   
|  `http://localhost:8080/api/v1/funcionarios/editar/{cpf}`        |    PATCH       |  Editar funcionário por CPF                    |                                                        

#### Propostas Endpoints

|       Rota           |    Método    |                   Descrição                    |                                                                         
|   ---------------     | :----------: |  ----------------------------------------------  |                                                                           
|  `http://localhost:8080/api/v1/propostas`            |    POST      |  Cadastrar uma proposta com um funcionário                               | 
|  `http://localhost:8080/api/v1/propostas/iniciar-votacao`            |    PATCH       |  Iniciar a votação de uma proposta com um funcionário                             |   
|  `http://localhost:8080/api/v1/propostas/votar`        |    POST       |  Voto de um funcionário                       |   
|  `http://localhost:8080/api/v1/propostas/{propostaTitulo}`        |    GET       |  Buscar uma proposta por título                    |                                                        

#### Resultados Endpoints

|       Rota           |    Método    |                   Descrição                    |                                                                         
|   ---------------     | :----------: |  ----------------------------------------------  |                                                                           
|  `http://localhost:8080/api/v1/resultados`            |    GET      |  Buscar por todas as propostas                               | 
|  `http://localhost:8080/api/v1/resultados/{propostaTitulo}`            |    GET       |  Buscar por todos as propostas com o mesmo título                             |   

### Testes

Para a realização dos testes das apis de Propostas e Resultados é necessário que os containers do Kafka no docker estejam em execução. E para todas as apis é necessários que o Eureka Server esteja em execução
