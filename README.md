---

# 📚 API da Livraria

---

## 🔧 Estrutura Geral

Este projeto é uma **API RESTful** desenvolvida com **Java e Spring Boot**, conteinerizada com **Docker** e conectada a um banco de dados relacional (PostgreSQL). A API oferece funcionalidades completas para gerenciamento de uma livraria online: livros, usuários, pedidos, avaliações e administração.

---

## ✅ Funcionalidades que serão implementadas

### 1. **Catálogo de Livros**

* Criar entidade `Book`
* Controlador REST para:

  * Listar todos os livros
  * Ver detalhes de um livro
  * Filtrar por autor, gênero, idioma e preço
  * Buscar por título ou ISBN
* Relacionamentos com autor, editora e gênero

---

### 2. **Autores**

* Entidade `Author`
* Endpoints para:

  * Listar autores
  * Ver detalhes
  * Criar, editar e excluir autores (admin)
* Um autor pode ter vários livros

---

### 3. **Editoras**

* Entidade `Publisher`
* Endpoints para:

  * Listar editoras
  * CRUD completo (admin)
* Relacionamento com livros (1\:N)

---

### 4. **Gêneros**

* Entidade `Genre`
* Endpoints para:

  * Listar e gerenciar gêneros
  * Filtrar livros por gênero

---

### 5. **Usuários / Clientes**

* Entidade `User`
* Cadastro e login com JWT
* Endpoints para:

  * Criar conta
  * Autenticar
  * Visualizar e editar perfil
  * Ver histórico de pedidos
  * Adicionar livros aos favoritos
* Proteção de rotas com `Spring Security`

---

### 6. **Carrinho de Compras**

* Entidade `CartItem`
* Relacionamento com `User` e `Book`
* Funcionalidades:

  * Adicionar livro
  * Atualizar quantidade
  * Remover item
  * Ver total do carrinho

---

### 7. **Pedidos**

* Entidades `Order` e `OrderItem`
* Endpoints para:

  * Finalizar pedido
  * Ver pedidos do usuário
  * Ver status: preparando, enviado, entregue
  * Admin pode gerenciar todos os pedidos

---

### 8. **Avaliações e Comentários**

* Entidade `Review`
* Funcionalidades:

  * Avaliar livros (1 a 5 estrelas)
  * Comentar livros
  * Ver comentários e média de avaliações

---

### 9. **Administração**

* Permissões baseadas em roles (`ROLE_USER`, `ROLE_ADMIN`)
* Endpoints protegidos com `@PreAuthorize`
* Admin pode:

  * Criar, editar, excluir livros, autores, editoras e gêneros
  * Atualizar pedidos
  * Visualizar estatísticas

---

# 🛠️ Backend – O que será feito no Spring Boot

---

## 📦 Entidades principais (JPA)

* `Book`, `Author`, `Publisher`, `Genre`
* `User`, `CartItem`, `Order`, `OrderItem`, `Review`

## 🔁 Relacionamentos

* `Book` → `Author`, `Publisher`, `Genre` (muitos-para-um)
* `User` → `CartItem`, `Order`, `Review`
* `Order` → `OrderItem` (um-para-muitos)

---

## 🔐 Autenticação e Segurança

* JWT com `Spring Security`
* Criação de `AuthenticationFilter`, `JwtProvider`
* Roles: `USER` e `ADMIN`
* Anotações:

  * `@PreAuthorize("hasRole('ADMIN')")` para proteger endpoints de admin
  * `@Secured`, `@EnableGlobalMethodSecurity` habilitadas

---

## 🧱 Estrutura dos pacotes

```
/src/main/java/com/seuprojeto/livraria
├── controller
├── dto
├── entity
├── repository
├── service
├── config
├── security
└── LivrariaApplication.java
```

---

## 🐳 Integração com Docker

* `Dockerfile` para empacotar a aplicação Spring Boot
* `docker-compose.yml` com:

  * API (Spring Boot)
  * Banco PostgreSQL
* `.env` ou `application.yml` com:

  * Configuração do banco
  * Porta
  * JWT secret

---
