# Gerenciador de Tarefas

Aplicação web simples para gerenciar tarefas, usuários e categorias construída com **Spring Boot**, **Thymeleaf** e **H2** (banco em memória).

## Tecnologias

- **Java 21**
- **Spring Boot 3** (Spring MVC, Spring Data JPA, Thymeleaf)
- **H2** (banco em memória)
- **Maven** (wrapper incluído)

## Requisitos

- JDK 21 instalado
- Windows / PowerShell (os comandos abaixo usam PowerShell). Em Unix/macOS use `./mvnw` em vez de `mvnw.cmd`.

## Como executar (desenvolvimento)

1. Abrir um terminal (PowerShell) na pasta do projeto.
2. Executar:

   ```powershell
   .\mvnw.cmd spring-boot:run
   ```

3. Acessar a aplicação em:

   [http://localhost:8080](http://localhost:8080)

## Comandos úteis

- Empacotar:

  ```powershell
  .\mvnw.cmd package
  ```

- Rodar testes:

  ```powershell
  .\mvnw.cmd test
  ```

## Endpoints / Páginas principais

- Listar tarefas: [`/tarefas/listarTarefas`](http://localhost:8080/tarefas/listarTarefas)
- Criar nova tarefa: [`/tarefas/novo`](http://localhost:8080/tarefas/novo)
- Listar categorias: [`/listarCategoria`](http://localhost:8080/listarCategoria)
- Listar usuários: [`/usuarios/listarUsuarios`](http://localhost:8080/usuarios/listarUsuarios)
- Console H2: [`/h2-console`](http://localhost:8080/h2-console)
  - JDBC URL: `jdbc:h2:mem:tarefas`
  - Usuário: `sa` (senha vazia)

> [!TIP]
> Para acessar o console H2, use o JDBC URL acima e usuário `sa` sem senha.

## Seed de dados

A classe [`CarregaBaseDeDados`](src/main/java/com/sesi/tarefas/config/CarregaBaseDeDados.java) popula a base em memória com alguns usuários, categorias e tarefas iniciais ao iniciar a aplicação.

## Estrutura do projeto

```
src/
  main/
    java/
      com/sesi/tarefas/
        GerenciadorTarefasApplication.java
        config/CarregaBaseDeDados.java
        controller/
          TarefaCategoriaController.java
          TarefaController.java
          UsuarioController.java
        model/
          Prioridade.java
          StatusTarefa.java
          Tarefa.java
          TarefaCategoria.java
          Usuario.java
        repository/
          TarefaCategoriaRepository.java
          TarefaRepository.java
          UsuarioRepository.java
    resources/
      application.properties
      templates/
        formularioTarefa.html
        formularioTarefaCategoria.html
        formularioUsuario.html
        listarTarefaCategoria.html
        listarTarefas.html
        listarUsuarios.html
```

## Observações

- O projeto usa H2 em memória; todos os dados são perdidos ao reiniciar a aplicação.
- Para produção, substituir H2 por um banco persistente e adicionar criptografia para senhas.

## Licença

MIT

