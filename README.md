
# 📝 Todo API - ASP.NET Core + Entity Framework + SQLite

Uma API RESTful simples para gerenciamento de tarefas (To-Do List), construída com:

- ⚙️ **ASP.NET Core**
- 🛠 **Entity Framework Core**
- 💾 **SQLite**
- 🔄 **Migrations**
- 📬 Testes via **Postman**

> 🔗 Repositório: [github.com/jeffersonguilherme/TodoApiDotNet](https://github.com/jeffersonguilherme/TodoApiDotNet)

---

## 🚀 Funcionalidades

✔️ CRUD completo de tarefas:  
&nbsp;&nbsp;&nbsp;&nbsp;➕ Criar  
&nbsp;&nbsp;&nbsp;&nbsp;📋 Listar  
&nbsp;&nbsp;&nbsp;&nbsp;✏️ Atualizar  
&nbsp;&nbsp;&nbsp;&nbsp;🗑 Deletar  

🕓 Armazena a data de criação automaticamente  
✅ Marca tarefas como concluídas  
🎯 Estrutura pronta para evoluir com autenticação, filtros, paginação, etc.

---

## 🧠 Modelo de Dados

```csharp
public class Todo
{
    public int Id { get; set; }
    public string Title { get; set; }
    public bool Done { get; set; }
    public DateTime CreatedAt { get; set; }
}
```

---


## 📬 Endpoints da API

| Método | Rota         | Descrição                        |
|--------|--------------|----------------------------------|
| GET    | `/`          | Lista todas as tarefas           |
| GET    | `/{id:int}`  | Retorna uma tarefa específica    |
| POST   | `/`          | Cria uma nova tarefa             |
| PUT    | `/{id:int}`  | Atualiza uma tarefa existente    |
| DELETE | `/{id:int}`  | Remove uma tarefa existente      |

---

## 📦 Como executar o projeto

```bash
# Clone o repositório
git clone https://github.com/jeffersonguilherme/TodoApiDotNet.git
cd TodoApiDotNet

# Restaure os pacotes
dotnet restore

# Aplique as migrations
dotnet ef database update

# Rode o projeto
dotnet run
```

> A API estará disponível em: `https://localhost:5001` ou `http://localhost:5000`

---


## 🧪 Exemplos de uso com JSON (Postman ou Insomnia)

### ➕ Criar tarefa (POST `/`)

```json
{
  "id":1,
  "title": "Estudar ASP.NET Core",
  "done": false,
  "createdAt": "2025-04-16T10:00:00"
}
```

### 📋 Obter todas as tarefas (GET `/`)
```json
[
    {
      "id": 1,
      "title": "Estudar EF Core",
      "done": true,
      "createdAt": "2025-04-16T10:00:00"
    }
]
```

### 🔍 Obter tarefa por ID (GET `/{id}`)

Exemplo: `GET /1`  
```json
{
  "id": 1,
  "title": "Estudar EF Core",
  "done": true,
  "createdAt": "2025-04-16T10:00:00"
}
```

### ✏️ Atualizar tarefa (PUT `/{id}`)

Exemplo: `PUT /1`

```json
{
  "title": "Estudar EF Core",
  "done": true,
  "createdAt": "2025-04-16T10:00:00"
}
```

### 🗑 Deletar tarefa (DELETE `/{id}`)

Exemplo: `DELETE /1`  
Sem corpo de requisição.


---

## ⚙️ Configuração do banco de dados

Este projeto usa **SQLite** por padrão.  
Para mudar o banco, edite a string de conexão em `AppDbContext.cs`:

```csharp
    protected override void OnConfiguring(DbContextOptionsBuilder options)
    => options.UseSqlite("DataSource=app.db;Cache=Shared");
```

Quer usar SQL Server?

```csharp
 protected override void OnConfiguring(DbContextOptionsBuilder options)
        => options.UseSqlServer("Server=localhost,1433;Database=Todo;User ID=sa;Password=<YourPassword>;TrustServerCertificate=True");
```

---

## 🛣 Roadmap (melhorias futuras)

- [ ] 🔐 Autenticação com JWT
- [ ] 📄 Documentação interativa com Swagger
- [ ] ☁️ Deploy na nuvem (Render, Azure, etc)
- [ ] 🔍 Filtros, ordenação e paginação

---

## 📄 Licença

Distribuído sob a licença **MIT**.  
Veja o conteúdo em [`LICENSE`](LICENSE) para mais informações.

---

## 🤝 Contribuições

Sinta-se à vontade para abrir issues, enviar PRs ou dar sugestões!  
Todo feedback é bem-vindo 😄
