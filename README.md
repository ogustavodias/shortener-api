# URL Shortener

Projeto de estudo desenvolvido para explorar conceitos de desenvolvimento backend, APIs REST, persistência de dados e arquitetura de aplicações.

## Objetivo

O sistema permite transformar URLs longas em URLs curtas e realizar o redirecionamento para a URL original quando o código encurtado é acessado.

### Exemplo

URL original:

```text
https://www.exemplo.com/produtos/categoria/item?id=12345
```

URL encurtada:

```text
http://localhost:8080/abc123
```

Ao acessar a URL encurtada, o usuário é redirecionado automaticamente para a URL original.

---

## Funcionalidades

### MVP

* Criar uma URL encurtada
* Armazenar a associação entre URL original e código curto
* Redirecionar para a URL original
* Persistir dados em banco de dados

### Próximas evoluções

* Dockerização da aplicação
* Testes automatizados
* Documentação OpenAPI / Swagger
* Contador de acessos
* Métricas de observabilidade
* Cache com Redis
* URLs personalizadas
* Expiração de links
* Autenticação de usuários

---

## Arquitetura

Fluxo principal:

```text
Cliente
   |
   v
API REST
   |
   v
Banco de Dados
```

Fluxo de criação:

```text
POST /shorten
   |
   v
Gera código curto
   |
   v
Salva URL
   |
   v
Retorna código
```

Fluxo de redirecionamento:

```text
GET /{code}
   |
   v
Busca URL original
   |
   v
Retorna redirect HTTP
```

---

## Endpoints

### Criar URL curta

```http
POST /shorten
```

Request:

```json
{
  "url": "https://www.google.com"
}
```

Response:

```json
{
  "shortCode": "abc123"
}
```

### Redirecionar

```http
GET /abc123
```

Response:

```http
302 Found
Location: https://www.google.com
```

---

## Tecnologias

* Linguagem: TBD
* Framework: TBD
* Banco de Dados: PostgreSQL
* API: REST

---

## Como executar

Instruções serão adicionadas conforme a evolução do projeto.

---

## Motivação

Este projeto tem como objetivo praticar:

* Design de APIs REST
* Modelagem de dados
* Arquitetura em camadas
* Testes automatizados
* Observabilidade
* Cache
* Conceitos de escalabilidade