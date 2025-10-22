# Gerenciador de Tarefas

Aplicação web simples para gerenciar tarefas, usuários e categorias construída com Spring Boot, Thymeleaf e H2 (banco em memória).

## Tecnologias

- Java 21
- Spring Boot 3 (Spring MVC, Spring Data JPA, Thymeleaf)
- H2 (banco em memória)
- Maven (wrapper incluído)

## Requisitos

- JDK 21 instalado
- Windows / PowerShell (os comandos abaixo usam PowerShell). Em Unix/macOS use `./mvnw` em vez de `mvnw.cmd`.

## Como executar (desenvolvimento)

1. Abrir um terminal (PowerShell) na pasta do projeto.
2. Executar:

   .\mvnw.cmd spring-boot:run

3. Acessar a aplicação em:

   http://localhost:8080

## Comandos úteis

- Empacotar:

  .\mvnw.cmd package

- Rodar testes:

  .\mvnw.cmd test

## Endpoints / Páginas principais

- Listar tarefas: `http://localhost:8080/tarefas/listarTarefas`
- Criar nova tarefa: `http://localhost:8080/tarefas/novo`
- Listar categorias: `http://localhost:8080/listarCategoria`
- Listar usuários: `http://localhost:8080/usuarios/listarUsuarios`
- Console H2: `http://localhost:8080/h2-console`
  - JDBC URL: `jdbc:h2:mem:tarefas`
  - Usuário: `sa` (senha vazia)

## Seed de dados

A classe `com.sesi.tarefas.config.CarregaBaseDeDados` popula a base em memória com alguns usuários, categorias e tarefas iniciais ao iniciar a aplicação.

## Estrutura do projeto (pacotes relevantes)

- `com.sesi.tarefas` - classe principal `GerenciadorTarefasApplication`
- `com.sesi.tarefas.controller` - controladores web (TarefaController, UsuarioController, TarefaCategoriaController)
- `com.sesi.tarefas.model` - entidades e enums (Tarefa, Usuario, TarefaCategoria, Prioridade, StatusTarefa)
- `com.sesi.tarefas.repository` - repositórios Spring Data JPA
- `src/main/resources/templates` - templates Thymeleaf

## Observações

- O projeto usa H2 em memória; todos os dados são perdidos ao reiniciar a aplicação.
- Para produção, substituir H2 por um banco persistente e adicionar criptografia para senhas.

## Licença

MIT

