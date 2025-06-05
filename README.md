<h1>Projeto DSList - Intesivão Java Spring</h1> 

Este projeto foi desenvolvido durante o intensivão Java Spring do Professor Nélio Alves. O DSList é uma aplicação backend desenvolvida com Java e Spring Boot, permitindo a listagem e ordenação de jogos.


## 🚀 Tecnologias Utilizadas

- Java 17
- Spring Boot
- Spring Data JPA
- Hibernate
- Banco de Dados H2 (teste)
- PostgreSQL (produção)
- Maven

<h2>Modelo de domínio DSList</h2>

![image](https://github.com/user-attachments/assets/2ee875b4-5070-457c-b6da-d777d85bc52c)

## 🧱 Arquitetura em Camadas

Este projeto foi desenvolvido utilizando o padrão de **arquitetura em camadas**, que promove a separação de responsabilidades e facilita a manutenção do código.

A estrutura básica segue o modelo abaixo:

![image](https://github.com/user-attachments/assets/955aeed0-851e-4c25-9554-f4137c118ca5)

- **Camada de Controladores REST:** recebe as requisições HTTP do frontend.
- **DTOs (Data Transfer Objects):** objetos que trafegam dados entre as camadas.
- **Camada de Serviço:** contém a lógica de negócio da aplicação.
- **Entities / ORM:** representação das entidades do banco de dados.
- **Camada de Acesso a Dados:** interage com o banco de dados via repositórios (Spring Data JPA).

## 📄 Endpoints da API

### 🎮 Jogos

- **GET** `/games`  
  Retorna a lista de todos os jogos.

- **GET** `/games/{id}`  
  Retorna os detalhes de um jogo específico.

### 🗂️ Listas de Jogos

- **GET** `/lists`  
  Retorna todas as listas de jogos.

- **GET** `/lists/{listId}/games`  
  Retorna os jogos associados a uma lista específica.

- **POST** `/lists/{listId}/replacement`  
  Atualiza a posição de um jogo dentro da lista.  
  **Request body:**
  ```json
  {
    "sourceIndex": 1,
    "destinationIndex": 3
  }
