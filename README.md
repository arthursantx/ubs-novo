# Sistema de Cadastro de Pacientes – UBS

Aplicação full stack para cadastro e gestão de pacientes de uma Unidade Básica de Saúde (UBS). Projeto acadêmico desenvolvido em equipe no curso de Análise e Desenvolvimento de Sistemas da FATEC Ipiranga (2024).

## Funcionalidades

- Cadastro de pacientes com dados pessoais, contato, endereço e documentos
- CPF único por paciente (restrição no banco de dados)
- Listagem e consulta de pacientes
- Atualização e exclusão de registros

## Tecnologias

**Back-end:** Java 17 · Spring Boot 3.3 · Spring Web · Spring Data JPA · Hibernate · MariaDB (com configuração alternativa para PostgreSQL) · Maven

**Front-end:** Angular 17 · TypeScript · HTML · CSS

## API REST

| Método | Endpoint | Descrição |
|--------|----------|-----------|
| GET | `/api/paciente` | Lista todos os pacientes |
| GET | `/api/paciente/{id}` | Busca um paciente pelo ID |
| POST | `/api/paciente` | Cadastra um paciente |
| PUT | `/api/paciente/{id}` | Atualiza um paciente |
| DELETE | `/api/paciente/{id}` | Remove um paciente |

## Arquitetura

```
backend/   API REST em Spring Boot (entidade, repositório JPA e controller)
frontend/  Aplicação Angular (cadastro, lista e serviço HTTP de pacientes)
```

O front-end consome a API pelo `PacienteService`, que centraliza as chamadas HTTP.

## Como executar

**Back-end**

1. Instale o Java 17 e suba um MariaDB na porta 3307 com o schema `ubs`.
2. Ajuste a conexão em `backend/src/main/resources/application.properties`.
3. Rode a API:

```bash
cd backend
./mvnw spring-boot:run
```

A API fica disponível em `http://localhost:8087`.

**Front-end**

```bash
cd frontend
npm install
npm start
```

A aplicação abre em `http://localhost:4200`.

## Próximos passos

- Usar DTOs e Bean Validation nas requisições
- Padronizar o tratamento de erros da API
- Ampliar os testes automatizados
- Documentar a API com Swagger/OpenAPI
- Containerizar a aplicação com Docker
