# 🔐 Spring Security JWT Auth API

<p align="center">
  <img src="https://img.shields.io/badge/Java-21-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" alt="Java 21" />
  <img src="https://img.shields.io/badge/Spring_Boot-3.x-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white" alt="Spring Boot" />
  <img src="https://img.shields.io/badge/Spring_Security-6.x-6DB33F?style=for-the-badge&logo=springsecurity&logoColor=white" alt="Spring Security" />
  <img src="https://img.shields.io/badge/JWT-OAuth2_Resource_Server-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white" alt="JWT" />
  <img src="https://img.shields.io/badge/MySQL-8.0-4479A1?style=for-the-badge&logo=mysql&logoColor=white" alt="MySQL" />
  <img src="https://img.shields.io/badge/Docker-Compose-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker" />
  <img src="https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge" alt="License MIT" />
</p>

API RESTful de nível de produção construída com **Java 21** e **Spring Boot 3**, implementando **autenticação stateless com JSON Web Tokens (JWT)**, criptografia assimétrica com par de chaves RSA (Public/Private Key) e controle de acesso baseado em funções (**RBAC - Role-Based Access Control**).

---

## 🎯 Funcionalidades e Arquitetura

- 🔑 **Autenticação Stateless JWT**: Geração de tokens de acesso seguros assinados com par de chaves RSA.
- 🛡️ **Role-Based Access Control (RBAC)**: Diferenciação de perfis `ADMIN` e `BASIC`.
- 🐦 **CRUD de Recursos (Tweets/Posts)**: Regras de negócio seguras onde usuários comuns gerenciam suas próprias publicações e administradores possuem privilégios de moderação.
- 🐳 **Ambiente Dockerizado**: Banco de dados MySQL pré-configurado via Docker Compose.
- 🗄️ **Persistência & Migrations**: Spring Data JPA com Hibernate e inicialização automatizada de usuários com `CommandLineRunner`.

---

## 📋 Endpoints Principais

| Método | Endpoint | Acesso | Descrição |
| :--- | :--- | :--- | :--- |
| `POST` | `/login` | Público | Autentica usuário e retorna JWT Bearer Token |
| `POST` | `/users` | Público | Cadastro de novos usuários |
| `GET` | `/feed` | Autenticado | Feed paginado de publicações |
| `POST` | `/tweets` | Autenticado | Criar nova publicação vinculada ao token |
| `DELETE` | `/tweets/{id}` | Autenticado / RBAC | Exclui tweet (Autor ou ADMIN) |

---

## 🚀 Como Executar

### Pré-requisitos
- **Java JDK 21+**
- **Maven** (ou wrapper incluso `./mvnw`)
- **Docker & Docker Compose**

### 1. Iniciar Banco de Dados (MySQL via Docker)
```bash
docker-compose -f docker/docker-compose.yml up -d
```

### 2. Executar a Aplicação Spring Boot
```bash
# Linux/macOS:
./mvnw spring-boot:run

# Windows:
./mvnw.cmd spring-boot:run
```

A API estará disponível em `http://localhost:8080`.

---

## 📄 Licença

Este projeto está licenciado sob a licença [MIT](LICENSE).

---

<p align="center">Desenvolvido por <a href="https://github.com/arthurtvrs10">Arthur Tavares</a></p>
