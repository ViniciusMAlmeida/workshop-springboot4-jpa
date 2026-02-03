# 🛠️ Workshop Spring Boot 4 + JPA

Este repositório contém um **projeto de estudo/workshop em Spring Boot 4 com JPA (Hibernate)**, desenvolvido com o objetivo de consolidar fundamentos do backend Java moderno.

Focando em boas práticas como separação de camadas, API REST, persistência com JPA e tratamento global de exceções.

---

## 📌 Tecnologias utilizadas

* ☕ **Java 21** (ou compatível)
* 🌱 **Spring Boot 4**
* 🌐 **Spring Web / Spring MVC**
* 🗄️ **Spring Data JPA (Hibernate)**
* 🧪 **H2 Database** (configurável para outros bancos)
* 📦 **Maven**
* 🔄 **Jackson (JSON)**

---

## 🎯 Objetivo do projeto

Demonstrar, de forma prática, como construir uma **API REST** utilizando Spring Boot e JPA, aplicando conceitos fundamentais como:

* Arquitetura em camadas (Controller, Service, Repository)
* Persistência de dados com JPA
* Tratamento global de exceções
* Padronização de respostas de erro
* Serialização customizada de dados (ex.: datas)

Este projeto é voltado para **aprendizado e demonstração de conhecimento**, não sendo um sistema complexo ou de produção.

---

## 📂 Estrutura do projeto

```text
src/main/java/com/educandoweb/course
├── config          # Configurações da aplicação (ex.: Jackson)
├── entities        # Entidades JPA
├── repositories    # Repositórios Spring Data JPA
├── services        # Regras de negócio
│   └── exceptions  # Exceções de domínio
├── resources       # Controllers REST
│   └── exceptions  # Tratamento global de exceções
└── Application.java
```

Essa organização segue boas práticas recomendadas para aplicações Spring Boot.

---

## 🚀 Como executar o projeto

### 1️⃣ Clonar o repositório

```bash
git clone https://github.com/ViniciusMAlmeida/workshop-springboot4-jpa.git
cd workshop-springboot4-jpa
```

### 2️⃣ Build do projeto

```bash
./mvnw clean install
```

### 3️⃣ Executar a aplicação

```bash
./mvnw spring-boot:run
```

Ou execute diretamente pela IDE (IntelliJ / Eclipse) a classe principal anotada com `@SpringBootApplication`.

---

## 📡 Exemplos de endpoints

### 🔹 Buscar usuário por ID

```http
GET /users/{id}
```

#### Resposta de sucesso

```json
{
  "id": 1,
  "name": "Vinicius",
  "email": "vinicius@email.com"
}
```

#### Resposta de erro (404)

```json
{
  "timestamp": "2026-02-03T13:15:39Z",
  "status": 404,
  "error": "Resource not found",
  "message": "Resource not found. Id 10",
  "path": "/users/10"
}
```

O projeto possui um **handler global de exceções**, garantindo respostas padronizadas para erros.

---

## 🛡️ Tratamento de exceções

As exceções são tratadas de forma centralizada utilizando `@ControllerAdvice`, retornando um objeto de erro padrão (`StandardError`) com:

* Timestamp formatado
* Código HTTP
* Mensagem de erro
* Caminho da requisição

Isso melhora a legibilidade e a experiência de consumo da API.

---

📌 *Projeto desenvolvido para fins de estudo e portfólio.*
