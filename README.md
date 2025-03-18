# Expense-splitter-backend
# 💸 Expense Splitter Backend

A robust ASP.NET Core Web API that enables users to split expenses, manage groups, track settlements, and handle user authentication using JWT. This backend powers an expense-sharing application ideal for friends, roommates, or teams managing shared costs.

---

## 🚀 Features

- 🧑‍🤝‍🧑 **User Management**: Register, login, and manage users with secure password hashing.
- 🏘 **Group Management**: Create groups, invite members, accept/reject invitations, and leave/delete groups.
- 💵 **Expense Tracking**: Add expenses, split among members, and track individual shares.
- 🤝 **Settlements**: Settle up expenses with detailed tracking (amount, method, notes).
- 📊 **Balances Calculation**: Compute who owes whom and how much, per group.
- 🔐 **JWT Authentication**: Secure access using token-based authentication.
- 📄 **Swagger UI**: Interactive API documentation and testing via Swagger.

---

## 🛠️ Tech Stack

- **Backend**: ASP.NET Core 8.0 Web API
- **Database**: SQL Server (via Entity Framework Core)
- **Authentication**: JWT (JSON Web Tokens)
- **Password Hashing**: PBKDF2 (via HMACSHA512)
- **API Docs**: Swagger / OpenAPI
- **Containerization**: Docker (optional)

---

## ⚙️ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/JUPUDIATHREAYASAKALYAN/Expense-splitter-backend.git
cd Expense-splitter-backend
2. Update Configuration
Edit appsettings.json to match your SQL Server setup:
"ConnectionStrings": {
  "DefaultConnection": "Server=YOUR_SERVER;Database=ExpenseSplitterDb;Trusted_Connection=True;"
},
"Jwt": {
  "Key": "YourVerySecureKeyHereAtLeast64BytesLong...",
  "Issuer": "ExpenseSplitterApi",
  "Audience": "ExpenseSplitterClient"
}
3. Database Migration
Ensure the database is created and up to date:

bash
Copy
Edit
dotnet ef database update
4. Run the Application
bash
Copy
Edit
dotnet run
API will be available at:
http://localhost:7156/swagger for Swagger UI
Or use launchSettings.json profiles.

🐳 Docker Support
Build and run using Docker:

bash
Copy
Edit
docker build -t expense-splitter-api .
docker run -p 5000:80 expense-splitter-api
🔐 Authentication
Register and login endpoints return a JWT token.
Include the token in the Authorization header for protected routes:
makefile
Copy
Edit
Authorization: Bearer <your_token_here>
📂 Project Structure
cpp
Copy
Edit
/Controllers        // API endpoints (Auth, Group, Expense)
/DTOs              // Data Transfer Objects
/Models            // Entity Framework models
/Services          // Token and Password services
/Data              // ApplicationDbContext and EF configuration
/Migrations        // EF Core migrations
Program.cs         // Application setup and middleware
Dockerfile         // Docker configuration
🧪 API Testing with Swagger
Visit http://localhost:7156/swagger after running the project to explore and test all endpoints interactively.
