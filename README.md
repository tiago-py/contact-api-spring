

# Contact API

Esta é uma API REST para gerenciamento de contatos, construída com Spring Boot. Ela fornece endpoints para criar, listar, buscar, atualizar e excluir contatos em um sistema de gerenciamento.

## Endpoints

### 1. Criar Novo Contato

- **URL:** `/api/contacts`
- **Método:** `POST`
- **Descrição:** Cria um novo contato no sistema.
- **Corpo da Requisição:**
  ```json
  {
    "firstName": "John",
    "lastName": "Doe",
    "email": "johndoe@example.com",
    "phoneNumber": "123-456-7890"
  }
  ```
- **Resposta de Sucesso:**
    - **Código:** `201 Created`
    - **Corpo:** Retorna o objeto do contato criado, incluindo o `id` gerado automaticamente.
  ```json
  {
    "id": 1,
    "firstName": "John",
    "lastName": "Doe",
    "email": "johndoe@example.com",
    "phoneNumber": "123-456-7890"
  }
  ```

### 2. Listar Todos os Contatos

- **URL:** `/api/contacts`
- **Método:** `GET`
- **Descrição:** Retorna uma lista de todos os contatos.
- **Resposta de Sucesso:**
    - **Código:** `200 OK`
    - **Corpo:** Uma lista de objetos de contato.
  ```json
  [
    {
      "id": 1,
      "firstName": "John",
      "lastName": "Doe",
      "email": "johndoe@example.com",
      "phoneNumber": "123-456-7890"
    },
    {
      "id": 2,
      "firstName": "Jane",
      "lastName": "Smith",
      "email": "janesmith@example.com",
      "phoneNumber": "987-654-3210"
    }
  ]
  ```

### 3. Buscar Contato por ID

- **URL:** `/api/contacts/{id}`
- **Método:** `GET`
- **Descrição:** Busca um contato específico pelo `id`.
- **Parâmetro de URL:** `id` (inteiro) - ID do contato.
- **Resposta de Sucesso:**
    - **Código:** `200 OK`
    - **Corpo:** Objeto do contato correspondente.
  ```json
  {
    "id": 1,
    "firstName": "John",
    "lastName": "Doe",
    "email": "johndoe@example.com",
    "phoneNumber": "123-456-7890"
  }
  ```
- **Erro:**
    - **Código:** `404 Not Found` - Se o contato não for encontrado.

### 4. Atualizar Contato

- **URL:** `/api/contacts/{id}`
- **Método:** `PUT`
- **Descrição:** Atualiza um contato existente.
- **Parâmetro de URL:** `id` (inteiro) - ID do contato.
- **Corpo da Requisição:**
  ```json
  {
    "firstName": "John",
    "lastName": "Doe",
    "email": "john.updated@example.com",
    "phoneNumber": "111-222-3333"
  }
  ```
- **Resposta de Sucesso:**
    - **Código:** `200 OK`
    - **Corpo:** Retorna o contato atualizado.
  ```json
  {
    "id": 1,
    "firstName": "John",
    "lastName": "Doe",
    "email": "john.updated@example.com",
    "phoneNumber": "111-222-3333"
  }
  ```
- **Erro:**
    - **Código:** `404 Not Found` - Se o contato não for encontrado.

### 5. Excluir Contato

- **URL:** `/api/contacts/{id}`
- **Método:** `DELETE`
- **Descrição:** Exclui um contato pelo `id`.
- **Parâmetro de URL:** `id` (inteiro) - ID do contato.
- **Resposta de Sucesso:**
    - **Código:** `204 No Content` - Se a exclusão foi bem-sucedida.
- **Erro:**
    - **Código:** `404 Not Found` - Se o contato não for encontrado.

## Configuração e Execução

Para executar este projeto, você precisa do [Java 11+](https://www.oracle.com/java/technologies/javase-downloads.html) e [Maven](https://maven.apache.org/) instalados.

### Passos para Execução

1. Clone o repositório:
   ```bash
   git clone https://github.com/seu_usuario/contact-api.git
   cd contact-api
   ```

2. Compile e execute o projeto:
   ```bash
   mvn spring-boot:run
   ```

3. A API estará disponível em `http://localhost:8080/api/contacts`.

## Estrutura do Projeto

- **Controller**: `ContactController.java` - contém todos os endpoints REST.
- **Model**: `Contact.java` - representa a entidade `Contact`.
- **Repository**: `ContactRepository.java` - interface para operações CRUD.

## Tecnologias Utilizadas

- **Spring Boot** - Framework para desenvolvimento rápido de aplicações Java.
- **Spring Data JPA** - Abstração para operações com banco de dados.
- **H2 Database (ou outro banco)** - Banco de dados em memória para desenvolvimento rápido.

## Autor

Desenvolvido por **Tiago Braga e Gustavo Soares**.

---

**Observação:** Este é um projeto de exemplo para fins de aprendizado e não está otimizado para produção.
