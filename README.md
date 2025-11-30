# CRUD de Veículos

## Descrição do Projeto
Este projeto é um **CRUD completo de veículos**, desenvolvido como teste técnico. Ele permite gerenciar veículos, clientes e vendas, com autenticação de usuários via **JWT**.  
O backend foi construído com **Spring Boot 4.0.0** e **Java 21**, e o frontend com **Angular**, utilizando recursos modernos como **Reactive Forms**.

O objetivo é demonstrar habilidades em desenvolvimento full-stack, segurança, persistência de dados e boas práticas de arquitetura.

---

## Tecnologias Utilizadas

### Backend
- **Java 21**
- **Spring Boot 4.0.0**
- **Spring Security** com **JWT 0.11.5**
- **Spring Data JPA / Hibernate**
- **MySQL**
- **Postman** para testes de API
- Maven para gerenciamento de dependências

### Frontend
- **Angular**
- **ReactiveFormsModule**
- **HttpClient** para comunicação com o backend
- HTML, CSS e TypeScript

---

## Funcionalidades

### Autenticação e Usuários (`/auth`)
- Registro de usuários (Admin e Cliente)
- Login com geração de **JWT**
- Listagem de usuários (Admin)
- Consulta de usuário por ID
- Exclusão de usuários (Admin)

### Clientes (`/clientes`)
- Consulta de clientes
- Atualização de clientes (Admin)
- Exclusão de clientes (Admin, altera status e remove do banco)
- Listagem de todos os clientes (Admin)

### Veículos (`/veiculos`)
- Cadastro, atualização e exclusão de veículos (Admin)
- Consulta de veículo por ID
- Listagem de todos os veículos

### Vendas (`/vendas`)
- Registro de vendas (Cliente/Admin)
- Consulta de venda por ID
- Listagem de todas as vendas (Admin)

---

## Estrutura de Endpoints

| Recurso        | Método | Endpoint            | Permissão       |
|----------------|--------|-------------------|----------------|
| Usuários       | POST   | `/auth/register`   | Todos          |
| Usuários       | POST   | `/auth/login`      | Todos          |
| Usuários       | GET    | `/auth/`           | Admin          |
| Usuários       | GET    | `/auth/{id}`       | Todos          |
| Usuários       | DELETE | `/auth/{id}`       | Admin          |
| Clientes       | GET    | `/clientes/`       | Admin          |
| Clientes       | GET    | `/clientes/{id}`   | Todos          |
| Clientes       | PUT    | `/clientes/{id}`   | Admin          |
| Clientes       | DELETE | `/clientes/{id}`   | Admin          |
| Veículos       | GET    | `/veiculos/`       | Todos          |
| Veículos       | GET    | `/veiculos/{id}`   | Todos          |
| Veículos       | POST   | `/veiculos/`       | Admin          |
| Veículos       | PUT    | `/veiculos/{id}`   | Admin          |
| Veículos       | DELETE | `/veiculos/{id}`   | Admin          |
| Vendas         | POST   | `/vendas/`         | Cliente/Admin  |
| Vendas         | GET    | `/vendas/`         | Admin          |
| Vendas         | GET    | `/vendas/{id}`     | Todos          |

---

## Como Rodar o Projeto

### Backend
1. Clone o repositório:

```bash
git clone <URL_DO_REPOSITORIO>
cd crudVeiculos-Completo
```
Obs: Você pode clonar e executar backend e frontend separadamente.

---

#### Configuração do MySQL

Crie um banco de dados para o projeto.

Atualize o arquivo application.properties com usuário, senha e nome do banco.

---
#### Configuração do pom.xml
Certifique-se de que o Java esteja configurado para a versão 21.

Confira se as dependências estão corretas: Spring Boot 4.0.0, JJWT 0.11.5, MySQL Connector, Spring Security, etc.

---

#### Instale Dependências e Rode o Backend
```bash
mvn clean install
mvn spring-boot:run
```
## Frontend
Navegue até a pasta do frontend:

```bash
cd CRUDVEICULOS-FRONT
npm install
```
Isso criará a pasta node_modules com todas as bibliotecas necessárias.

#### Rode a aplicação Angular:
---

```bash
ng serve
Acesse a aplicação em: http://localhost:4200
```

Observação: Certifique-se de que o backend esteja rodando para que o frontend consiga se comunicar com a API.

---
### Testes de API
Todas as requisições podem ser testadas via Postman ou Insomnia.

Para rotas protegidas, inclua o JWT no header:
```bash
Authorization: Bearer <token>
```

## Estrutura do Projeto (Completa)
### Backend
---
```bash
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── io/github/desafioTecnico/crudVeiculos/
│   │   │       ├── controller/
│   │   │       ├── dto/
│   │   │       ├── enums/
│   │   │       ├── exceptions/
│   │   │       ├── model/
│   │   │       ├── repository/
│   │   │       ├── security/
│   │   │       ├── service/
│   │   │       └── CrudVeiculosApplication.java
│   │   └── resources/
│   │       └── application.properties
│   └── test/
├── target/
├── .gitignore
├── .gitattributes
├── HELP.md
├── mvnw
├── mvnw.cmd
└── pom.xml

```
### Frontend
---
```bash

CRUDVEICULOS-FRONT/
├── node_modules/
├── public/
└── src/
    └── app/
        ├── dashboard-admin/
        ├── dashboard-editar-cliente/
        ├── dashboard-inclusao/
        ├── footer/
        ├── header/
        ├── home/
        ├── login/
        ├── pagina-de-compra/
        ├── pagina-de-confirmacao/
        ├── registro/
        └── services/
    ├── app.config.ts
    ├── app.css
    ├── app.html
    ├── app.routes.ts
    ├── app.spec.ts
    ├── app.ts
    ├── index.html
    ├── main.ts
    └── styles.css
```
## Autor

**Jefferson Silva Geronimo**  

GitHub: [Jefferson-Silva-Geronimo](https://github.com/Jefferson-Silva-Geronimo/)
