📚 Projeto da API de Livraria – Backend (Node.js + Docker)

🧾 Visão Geral

Este projeto consiste na construção de uma API RESTful para uma livraria online, com backend desenvolvido em JavaScript (Node.js) e conteinerizado com Docker. O sistema permitirá gerenciamento completo do catálogo de livros, carrinho, pedidos, avaliações e administração.

---

🧱 Tecnologias Utilizadas

Linguagem: JavaScript (Node.js)

Framework: Express.js

Banco de dados: PostgreSQL ou MongoDB

Autenticação: JWT

Docker: Para empacotamento e execução de todo o ambiente (API + banco)

Bibliotecas úteis:

express, cors, jsonwebtoken, mongoose ou pg, dotenv, etc.

---

📦 Funcionalidades da API

1. 📖 Catálogo de Livros

Listar todos os livros

Ver detalhes de um livro

Buscar por título ou ISBN

Filtrar por autor, gênero, idioma, faixa de preço


2. 👤 Autores

Listar autores

Ver detalhes

Associar livros a autores

CRUD para admin


3. 🏢 Editoras

Listar editoras

Associar livros

CRUD para admin


4. 🏷️ Gêneros

Listar gêneros

Filtrar livros por gênero

CRUD para admin


5. 👥 Usuários / Clientes

Cadastro e login

Ver/editar perfil

Histórico de compras

Marcar favoritos


6. 🛒 Carrinho de Compras

Adicionar/remover/editar itens

Ver resumo do carrinho


7. 🧾 Pedidos

Finalizar pedido

Ver histórico e status

Gerenciamento por admin


8. ⭐ Avaliações e Comentários

Avaliar livros (1-5 estrelas)

Comentar e visualizar comentários


9. ⚙️ Administração (Área Protegida)

Gerenciar livros, autores, editoras e gêneros

Acompanhar pedidos

Ver estatísticas:

Mais vendidos

Melhor avaliados

---

🛡️ Autenticação e Autorização

Sistema baseado em JWT

Rotas públicas e rotas protegidas

Regras de acesso para:

Usuário comum

Administrador

---

🐳 Docker

O projeto será executado em containers com Docker:

API: Container com Node.js

Banco de dados: PostgreSQL ou MongoDB em container separado

Arquivo docker-compose.yml para orquestração dos serviços
