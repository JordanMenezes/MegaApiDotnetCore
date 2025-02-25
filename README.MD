# Documentação Completa do Repositório MegaApiDotnetCore

## Índice

1. [Descrição do Projeto](#descrição-do-projeto)
2. [Características Principais](#características-principais)
3. [Tecnologias Utilizadas](#tecnologias-utilizadas)
4. [Estrutura do Projeto](#estrutura-do-projeto)
5. [Endpoints da API](#endpoints-da-api)
6. [Configuração do Ambiente](#configuração-do-ambiente)
7. [Uso da API](#uso-da-api)
8. [Testes](#testes)
9. [Dependências](#dependências)
10. [Licença](#licença)
11. [Contribuição](#contribuição)
12. [Contato](#contato)

## Descrição do Projeto

O **MegaApiDotnetCore** é uma API desenvolvida em **.NET Core** que oferece acesso a informações sobre os vilões do jogo **Mega Man**. O principal objetivo deste projeto é fornecer uma interface RESTful para acessar e manipular dados relacionados aos robôs do jogo, permitindo a integração com diferentes aplicações e serviços.

## Características Principais

- **Interface RESTful**: A API segue os princípios REST para permitir fácil uso e integração.
- **Formato JSON**: Os dados são retornados em formato JSON, que é amplamente utilizado e fácil de manipular.
- **Persistência de Dados**: Utiliza o Entity Framework Core para gerenciar a persistência de dados em um banco de dados.
- **Documentação de API**: A API inclui documentação que pode ser acessada via Swagger.
- **Suporte a CRUD**: Permite operações de criação, leitura, atualização e exclusão (CRUD) para os vilões do Mega Man.

## Tecnologias Utilizadas

- **.NET Core 3.1**: Framework para desenvolvimento de aplicações.
- **Entity Framework Core**: ORM (Object-Relational Mapping) que facilita o acesso ao banco de dados.
- **ASP.NET Core**: Plataforma para construir aplicativos web.
- **Newtonsoft.Json**: Biblioteca para manipulação de dados em formato JSON.
- **Swagger**: Ferramenta para documentação e teste de APIs.

## Estrutura do Projeto

A estrutura do projeto segue a convenção padrão do ASP.NET Core e está organizada da seguinte forma:

```plaintext
src
├── MegaApiDotnetCore
│   ├── Controllers         [Controladores que gerenciam as rotas]
│   ├── Models              [Modelos de dados]
│   ├── Services            [Serviços e regras de negócio]
│   ├── Database            [Estruturas relacionadas ao banco de dados]
│   │   ├── Entities       [Modelos de entidades do banco]
│   │   ├── DTOs           [Modelos de transferência de dados]
│   │   ├── Migrations      [Migrações do banco de dados]
│   │   ├── Context         [Configuração do contexto do EF]
│   ├── Middleware          [Middleware personalizados]
│   ├── Startup.cs          [Configuração da aplicação]
│   └── Program.cs          [Ponto de entrada da aplicação]
```

## Endpoints da API

Abaixo estão os principais endpoints da API:

| Método | Endpoint               | Descrição                                    |
|--------|------------------------|----------------------------------------------|
| GET    | /api/v1/robots         | Retorna uma lista de todos os robôs         |
| GET    | /api/v1/robots/{id}    | Retorna detalhes de um robô específico pelo ID |
| POST   | /api/v1/robots         | Cria uma nova entrada de robô                |
| PUT    | /api/v1/robots/{id}    | Atualiza os dados de um robô específico     |
| DELETE | /api/v1/robots/{id}    | Remove um robô específico pelo ID            |

### Exemplo de Resposta

- **GET /api/v1/robots**

```json
[
    {
        "id": 1,
        "name": "Cut Man",
        "description": "Um robô com lâminas que corta tudo.",
        "weakness": "Thunder Beam"
    },
    {
        "id": 2,
        "name": "Guts Man",
        "description": "Um robô forte que pode levantar rochas.",
        "weakness": "Ice Slasher"
    }
]
```

## Configuração do Ambiente

Para configurar o ambiente para executar a API, siga os passos abaixo:

1. **Clone o repositório**:
   ```bash
   git clone https://github.com/felipeAguiarCode/MegaApiDotnetCore.git
   cd MegaApiDotnetCore
   ```

2. **Restaure as dependências**:
   ```bash
   dotnet restore
   ```

3. **Configure a string de conexão do banco de dados**:
   - Abra o arquivo `appsettings.json` e configure a string de conexão para o seu banco de dados SQL Server.

4. **Execute as migrações do banco de dados**:
   ```bash
   dotnet ef database update
   ```

5. **Execute a aplicação**:
   ```bash
   dotnet run
   ```

## Uso da API

- Para testar os endpoints, você pode usar ferramentas como [Postman](https://www.postman.com/) ou [Insomnia](https://insomnia.rest/).
- O Swagger está disponível na rota `/swagger` após a aplicação ser iniciada, permitindo explorar e testar a API diretamente do navegador.

## Testes

O projeto inclui testes unitários que podem ser executados para garantir que a aplicação funcione conforme o esperado. Para executar os testes, utilize o seguinte comando:

```bash
dotnet test
```

## Dependências

| Pacote                              | Versão  | Link   |
|-------------------------------------|---------|--------|
| Microsoft.EntityFrameworkCore       | 3.1.8   | [NuGet](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore/) |
| Microsoft.EntityFrameworkCore.Design | 3.1.8   | [NuGet](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore.Design/) |
| Microsoft.EntityFrameworkCore.SqlServer | 3.1.8 | [NuGet](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore.SqlServer/) |
| Newtonsoft.Json                     | 12.0.2  | [NuGet](https://www.nuget.org/packages/Newtonsoft.Json/) |

## Licença

Este projeto está licenciado sob os termos da [MIT License](https://opensource.org/licenses/MIT).

## Contribuição

Contribuições são bem-vindas! Para contribuir, siga estas etapas:

1. Faça um fork do repositório.
2. Crie uma nova branch para sua feature (`git checkout -b feature/nome-da-feature`).
3. Realize suas alterações e faça commit (`git commit -m 'Adiciona uma nova feature'`).
4. Envie sua branch para o GitHub (`git push origin feature/nome-da-feature`).
5. Abra um pull request no repositório original.

## Contato

Desenvolvedor: Felipe Aguiar  
GitHub: [felipeAguiarCode](https://github.com/felipeAguiarCode)  
Email: felipe.aguiar@example.com

Para mais informações, acesse o repositório no [GitHub](https://github.com/felipeAguiarCode/MegaApiDotnetCore).