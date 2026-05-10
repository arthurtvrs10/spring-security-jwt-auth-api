# spring-security-jwt-auth-api

## 📌 Sobre o projeto

Esse projeto é uma Api com aplicação backend construída com Spring Boot com foco em:

* Autenticação JWT
* Autorização com Spring Security
* Controle de Roles (ADMIN e BASIC)
* CRUD de tweets
* API REST
* Persistência com JPA/Hibernate
* Banco de dados MySQL

O projeto foi criado com objetivo de aprendizado prático sobre segurança em APIs modernas usando Java.

---

## 🚀 Tecnologias utilizadas

* Java 21
* Spring Boot
* Spring Security
* Spring Data JPA
* JWT (JSON Web Token)
* Hibernate
* MySQL
* Maven

---

## 🔐 Funcionalidades

### Usuários

* Cadastro de usuários
* Login autenticado com JWT
* Criptografia de senha com BCrypt
* Controle de permissões com roles

### Tweets

* Criar tweets
* Listar tweets
* Deletar tweets
* Proteção de rotas autenticadas

---

## 📂 Estrutura do projeto

```txt
src/main/java
 ├── config
 ├── controller
 ├── controller/dto
 ├── entities
 ├── repository
```

---

## ⚙️ Configuração do banco

### application.properties

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/mydb
spring.datasource.username=root
spring.datasource.password=senha

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

---

## 🔑 Autenticação JWT

### Login

```http
POST /login
```

### Body

```json
{
  "username": "admin",
  "password": "123"
}
```

### Resposta

```json
{
  "accessToken": "jwt-token",
  "expiresIn": 300
}
```

---

## 🛡️ Rotas protegidas

Para acessar rotas protegidas:

```http
Authorization: Bearer SEU_TOKEN
```

---

## 👤 Roles

### ADMIN

* Pode acessar endpoints administrativos
* Pode listar usuários

### BASIC

* Pode criar tweets
* Pode acessar endpoints comuns

---

## 📮 Endpoints

### Usuários

| Método | Endpoint | Descrição       |
| ------ | -------- | --------------- |
| POST   | /users   | Criar usuário   |
| GET    | /users   | Listar usuários |

---

### Autenticação

| Método | Endpoint | Descrição |
| ------ | -------- | --------- |
| POST   | /login   | Gerar JWT |

---

### Tweets

| Método | Endpoint     | Descrição     |
| ------ | ------------ | ------------- |
| POST   | /tweets      | Criar tweet   |
| DELETE | /tweets/{id} | Deletar tweet |

---

## 🧠 Conceitos praticados

* JWT Authentication
* Authorization Server
* OAuth2 Resource Server
* BCrypt Password Encoder
* Roles e Authorities
* Stateless Authentication
* REST APIs
* Relacionamentos JPA
* ManyToMany
* DTO Pattern
* Segurança em APIs

---

## ▶️ Como executar

```bash
# clonar repositório
git clone https://github.com/seu-user/devtweet-api.git](https://github.com/arthurtvrs10/spring-security-jwt-auth-api.git

# entrar na pasta
cd spring-security-jwt-auth-api

# executar aplicação
./mvnw spring-boot:run
```

---

## 📖 Objetivo

Este projeto foi desenvolvido com foco em estudo e aprofundamento em:

* Spring Security
* JWT
* APIs REST modernas
* Arquitetura backend
* Segurança de aplicações Java

