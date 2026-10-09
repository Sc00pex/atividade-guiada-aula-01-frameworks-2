# API de tarefas

Projeto da atividade guiada, feito com Spring Boot 4.1.1, Java 21 e Maven. A API permite criar, consultar, atualizar e excluir tarefas, que ficam salvas em memória.

## Como iniciar

Com o Java 21 instalado, abra o PowerShell na pasta do projeto e execute:

```powershell
cd "atividade-guiada-aula-01-frameworks-2"
.\mvnw.cmd spring-boot:run
```

Se o projeto estiver em outro lugar, ajuste o caminho. Aguarde aparecer `Started TaskApiApplication` e mantenha o terminal aberto. Para encerrar, use `Ctrl+C`.

## Como testar

Acesse <http://localhost:8080/tasks>. Se aparecer `[]`, a API está funcionando e ainda não há tarefas cadastradas.

No Postman, use estas rotas:

| Método | Rota | O que faz |
| --- | --- | --- |
| GET | /tasks | Lista as tarefas |
| GET | /tasks/{id} | Busca uma tarefa |
| POST | /tasks | Cria uma tarefa |
| PUT | /tasks/{id} | Atualiza uma tarefa |
| DELETE | /tasks/{id} | Exclui uma tarefa |

Para criar, envie um POST para `http://localhost:8080/tasks`, com **Body → raw → JSON**:

```json
{
  "id": 0,
  "title": "Casa",
  "description": "Organizar as tarefas de casa",
  "dueDate": "2026-12-31T18:00:00"
}
```

O ID será gerado automaticamente. Use o ID retornado no lugar de `{id}` nas outras rotas. Para atualizar, envie um PUT com os novos dados no mesmo formato.

Ao reiniciar a aplicação, as tarefas são apagadas.
