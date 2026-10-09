# API CRUD para controle de tarefas

Atividade guiada com Spring Boot 4.1.1, Java 21, Maven e Spring Web.
As tarefas são armazenadas em uma lista em memória.

## Executar

No Windows, dentro da pasta do projeto:

```powershell
.\mvnw.cmd spring-boot:run
```

No Linux ou macOS:

```sh
./mvnw spring-boot:run
```

A API estará disponível em `http://localhost:8080/tasks`.

## Operações

| Método | Caminho | Operação |
| --- | --- | --- |
| GET | /tasks | Listar todas as tarefas |
| GET | /tasks/{id} | Buscar uma tarefa pelo ID |
| POST | /tasks | Criar uma tarefa |
| PUT | /tasks/{id} | Atualizar uma tarefa |
| DELETE | /tasks/{id} | Excluir uma tarefa |

Para POST e PUT, use `Content-Type: application/json` e um corpo como:

```json
{
  "id": 0,
  "title": "Casa",
  "description": "Organizar as tarefas de casa",
  "dueDate": "2026-12-31T18:00:00"
}
```

Na criação, use ID igual a zero para que ele seja gerado automaticamente. Na atualização,
o ID usado é o informado no caminho. O campo `dueDate` contém data e horário,
conforme o tipo `LocalDateTime` do modelo fornecido no trabalho.
