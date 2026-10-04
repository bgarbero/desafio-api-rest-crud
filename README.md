# Client CRUD API

API REST de CRUD de clientes, organizada em camadas (controller, service e repository), com paginação, validação de dados e tratamento de exceções.

Desafio do módulo de Backend da **Formação Desenvolvedor Moderno** da DevSuperior.

## 🛠 Tecnologias

- Java 21
- Spring Boot
- Spring Data JPA
- Bean Validation
- Banco de dados H2
- Maven

## 📌 Endpoints

| Método | Rota | Descrição |
|---|---|---|
| GET | `/clients?page=0&size=6&sort=name` | Busca paginada de clientes |
| GET | `/clients/{id}` | Busca de cliente por ID |
| POST | `/clients` | Inserção de novo cliente |
| PUT | `/clients/{id}` | Atualização de cliente |
| DELETE | `/clients/{id}` | Deleção de cliente |

Exemplo de corpo para POST e PUT:

```json
{
  "name": "Maria Silva",
  "cpf": "12345678901",
  "income": 6500.0,
  "birthDate": "1994-07-20",
  "children": 2
}
```

## ✅ Regras de validação

- **Nome:** não pode ser vazio
- **Data de nascimento:** não pode ser uma data futura

## ⚠️ Tratamento de exceções

| Situação | Resposta |
|---|---|
| ID não encontrado | `404 Not Found` |
| Dados inválidos | `422 Unprocessable Entity`, com as mensagens de validação de cada campo |

## ▶️ Como rodar

```bash
git clone https://github.com/bgarbero/desafio-api-rest-crud.git
cd desafio-api-rest-crud/clientcrud/clientcrud
./mvnw spring-boot:run
```

A API sobe em `http://localhost:8080`.

## 🧪 Cenários testados (Postman)

- Busca por ID existente e inexistente (404)
- Busca paginada
- Inserção válida e inválida (422)
- Atualização válida, inexistente (404) e inválida (422)
- Deleção existente e inexistente (404)

---

Feito por [Bruno Garbero](https://www.linkedin.com/in/bruno-garbero/)
