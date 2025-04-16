# 📝 Todo API - ASP.NET Core + EF + SQLite

Uma API RESTful simples para gerenciamento de tarefas (To-Do), construída com:

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

