## **Full-Stack User Management System**

**Tech Stack:**

* **Backend:** ASP.NET Core 8.0 Web API, Entity Framework Core, SQL Server
* **Frontend:** Vanilla JavaScript, HTML, CSS
* **Database:** Microsoft SQL Server

---

## **Objective**

Build a Full-Stack User Management System with the following features:

* Create, Read, Update, Delete (CRUD) Users
* Search Users by Name or Email
* Filter Users by Status (Active/Inactive)
* Sort Users by Age (Ascending/Descending)

---

## **Project Structure**

```
UserManagement/
├── Controllers/
│   └── UsersController.cs
├── Data/
│   └── AppDbContext.cs
├── Models/
│   └── User.cs
├── Migrations/
├── wwwroot/
│   ├── index.html
│   ├── app.js
│   ├── styles.css
├── Program.cs
├── appsettings.json
└── ...
```

---



### Configure Database

Updates the `appsettings.json` with SQL Server connection string:

```json
"ConnectionStrings": {
  "DefaultConnection": "Server=YOUR_SERVER;Database=UserManagementDb;Trusted_Connection=True;TrustServerCertificate=True;"
}
```

---

### Run Migrations

Initialize the database:

```bash
dotnet ef migrations add InitialCreate
dotnet ef database update
```
---
  

## **API Endpoints**

| HTTP Method | Route             | Description          |
| ----------- | ----------------- | -------------------- |
| POST        | `/api/users`      | Create a new user    |
| GET         | `/api/users`      | Get all users        |
| GET         | `/api/users/{id}` | Get user by ID       |
| PUT         | `/api/users/{id}` | Update existing user |
| DELETE      | `/api/users/{id}` | Delete user by ID    |

### **Search / Filter / Sort**

* Search: `?search=keyword` (Name or Email)
* Filter: `?status=active` or `?status=inactive`
* Sort: `?sort=age_asc` or `?sort=age_desc`

---

---

## **Database Schema**

The `User` table includes:

* `Id` (Primary Key)
* `Name` (Required)
* `Email` (Required, `[EmailAddress]`)
* `PhoneNumber` (Required)
* `Address` (Required)
* `IsActive` (Boolean, default `true`)
* `Age` (int)

##
<img width="1034" height="659" alt="14" src="https://github.com/user-attachments/assets/0fe47481-1046-49b2-89fa-37ffc607dc4a" />

## **API Responses**

All endpoints return JSON in the format:

```json
{
  "message": "Descriptive message",
  "data": [ /* single user or user list */ ]
}
```

---

## **Frontend**

### **UI Preview**

<img width="1366" alt="Dashboard" src="https://github.com/user-attachments/assets/5c214f99-3310-43bb-a4b8-e350f32437a8" />

### **Features**

## **Add User:** 
<img width="1366" alt="Add User" src="https://github.com/user-attachments/assets/e7b80694-7f75-4dfa-89ab-3d98a59c698c" />

## **Update User:** 
<img width="1366" alt="Update User" src="https://github.com/user-attachments/assets/8d1403e0-7bc4-49ec-8ec8-2812179f7474" />

## **Delete User:** 
<img width="1366" alt="Delete User" src="https://github.com/user-attachments/assets/72d6b8f1-4abe-4400-8fe9-d29a4bb4c9d1" />

## **Search By Name:** 
<img width="1366" alt="Search Name" src="https://github.com/user-attachments/assets/c76f3236-1b00-46dc-adb7-86591db5885a" />

## **Filter Active Users:** 
<img width="1366" alt="Active Users" src="https://github.com/user-attachments/assets/0f972fba-caa5-4573-9560-67225ac0177a" />

## **Filter Inactive Users:** 
<img width="1366" alt="Inactive Users" src="https://github.com/user-attachments/assets/453be246-3513-46cf-a7a4-83c596f5304e" />

## **Sort Age Ascending:**
<img width="1366" alt="Age Ascending" src="https://github.com/user-attachments/assets/c7a9814e-942c-4c24-aba5-7094339f6a02" />

## **Sort Age Descending:**
<img width="1357" alt="Age Descending" src="https://github.com/user-attachments/assets/186403a1-7c8d-4f45-8341-4d3797d24d75" />

---



---

## **How the Frontend Works**

* Uses **fetch API** to communicate with the backend.
* Renders the user list dynamically.
* Handles add/update/delete via forms.
* Supports live search, filtering, and sorting.
* All operations update the DOM in real-time.

---

## **Testing**

Tested thoroughly with **Postman**:

<img width="940" alt="Postman 1" src="https://github.com/user-attachments/assets/ecd1f050-f72d-408e-aec1-68ccdfaf2964" />
<img width="934" alt="Postman 2" src="https://github.com/user-attachments/assets/fd9c9ca3-ebe1-448a-b837-31db37a98731" />
<img width="937" alt="Postman 3" src="https://github.com/user-attachments/assets/3a36713d-6f77-4ccc-9e05-9e6452dc2835" />
<img width="937" alt="Postman 4" src="https://github.com/user-attachments/assets/b5883e35-e316-42f3-b487-d1738e9c0d41" />
<img width="937" alt="Postman 5" src="https://github.com/user-attachments/assets/901c3e80-b6ca-4dec-9412-f79c53a79e35" />
<img width="936" height="467" alt="8" src="https://github.com/user-attachments/assets/9802afbe-8518-4efd-8c96-c66f376cc453" />
<img width="934" height="574" alt="9" src="https://github.com/user-attachments/assets/2ddb2dc4-c139-4306-aa7e-a31d12f0c8e2" />
<img width="940" height="580" alt="10" src="https://github.com/user-attachments/assets/06f094d1-7936-4033-84d8-f61497ee4c6d" />
<img width="940" height="588" alt="11" src="https://github.com/user-attachments/assets/a1434b36-e459-40bb-9a5b-d01dbd9312d9" />
<img width="940" height="620" alt="12" src="https://github.com/user-attachments/assets/41484c47-a3e6-4bff-9bd1-2df3c5229c32" />
<img width="935" height="515" alt="13" src="https://github.com/user-attachments/assets/bfbdb458-c53b-4d6c-a395-5b90bc6b4290" />


---
### **Frontend Files**

## `index.html` 
<img width="937" alt="index.html" src="https://github.com/user-attachments/assets/47ab1412-db94-461b-80af-d4e1a44f01ce" />

## `app.js`
<img width="936" alt="app.js" src="https://github.com/user-attachments/assets/ff528e77-7204-478e-bfee-6baa08024ebc" />

## `styles.css`
<img width="939" alt="styles.css" src="https://github.com/user-attachments/assets/3e4e53d9-895b-40bf-b4e2-757a88f53746" />
---

## **Conclusion**

This project demonstrates a **complete full-stack CRUD application** with:

* **.NET Core Web API**
* **Entity Framework Core**
* **SQL Server**
* **Vanilla JavaScript**

