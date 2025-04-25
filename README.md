# 📚 Projeto Biblioteca - Spring Boot + MariaDB

Este projeto é uma API REST simples utilizando **Spring Boot** que demonstra um relacionamento entre duas entidades: `Autor` e `Livro`.

## 🧱 Estrutura do Projeto

biblioteca/ ├── src/ │ ├── main/ │ │ ├── java/com/david/biblioteca/ │ │ │ ├── controller/ │ │ │ │ ├── AutorController.java │ │ │ │ └── LivroController.java │ │ │ ├── model/ │ │ │ │ ├── Autor.java │ │ │ │ └── Livro.java │ │ │ └── repository/ │ │ │ ├── AutorRepository.java │ │ │ └── LivroRepository.java │ └── resources/ │ └── application.properties ├── pom.xml └── README.md

yaml
Copiar
Editar

---

## 🛠️ Tecnologias Utilizadas

- Java 21
- Spring Boot 3.x
- Spring Data JPA
- Lombok
- MariaDB via XAMPP
- Maven

---

## 🧩 Relacionamento entre entidades

- Um `Autor` pode ter vários `Livros` (**One-to-Many**).
- Cada `Livro` pertence a um único `Autor`.

---

## 🔌 Configuração do Banco de Dados (MariaDB)

1. **Instale o XAMPP** e inicie o serviço `MySQL`.

2. Acesse o `phpMyAdmin` via navegador:  
   `http://localhost/phpmyadmin`

3. Crie o banco de dados:

```sql
CREATE DATABASE biblioteca;
As tabelas serão geradas automaticamente com base nas entidades ao rodar a aplicação pela primeira vez.

⚙️ application.properties
properties
Copiar
Editar
spring.datasource.url=jdbc:mariadb://localhost:3306/biblioteca
spring.datasource.username=root
spring.datasource.password=

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MariaDBDialect
🧪 Testes com Postman ou Bruno
Autor
POST /autores
Cria um novo autor
Body (JSON):

json
Copiar
Editar
{
  "nome": "Machado de Assis",
  "nacionalidade": "Brasileira"
}
GET /autores
Lista todos os autores

GET /autores/{id}
Busca autor por ID

PUT /autores/{id}
Atualiza um autor

DELETE /autores/{id}
Remove um autor

Livro
POST /livros
Cria um novo livro
Body (JSON):

json
Copiar
Editar
{
  "titulo": "Dom Casmurro",
  "anoPublicacao": 1899,
  "autor": {
    "id": 1
  }
}
GET /livros
Lista todos os livros

GET /livros/{id}
Busca livro por ID

PUT /livros/{id}
Atualiza um livro

DELETE /livros/{id}
Remove um livro

🚀 Como rodar o projeto
Inicie o MariaDB via XAMPP.

Crie o banco biblioteca no phpMyAdmin.

Compile e rode o projeto:

bash
Copiar
Editar
./mvnw spring-boot:run
Acesse:
http://localhost:8080/livros ou http://localhost:8080/autores

👨‍💻 Autor
David Mendes
Projeto acadêmico de avaliação - CRUD com Spring Boot + MariaDB







