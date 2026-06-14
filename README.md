# ABCRetailByRH – Cloud Development B (CLDV6212) – Part 3 POE  
By **Riaad Hercules **

A complete cloud-backed retail web application built using **ASP.NET Core MVC**, integrated with **Azure SQL**, **Azure Storage (Tables, Queues, Blobs, Files)**, and **Azure Functions** for serverless order processing.  
This project demonstrates full deployment to **Azure App Service**, including authentication, cart functionality, product catalogue, order pipeline, file uploads, and serverless compute.

---

## 🌐 Live System Links

### 🔵 **Live Website (Azure App Service)**
https://abcretailbyrhweb-buh2cvhzb3b9dkgv.southafricanorth-01.azurewebsites.net/

### 🔵 **GitHub Repository**
https://github.com/herculesriaadst10258492/ABCRetailByRH-CLDV6212P3

### 🔵 **Unlisted YouTube Video Demonstration**
https://youtu.be/FjPzVC2yeM4

---

## 📌 Project Overview

ABCRetailByRH is a cloud-enabled retail system supporting:

- 👤 **SQL-based Authentication**
- 🛒 **Customer Cart with Azure SQL storage**
- 🛍️ **Product management using Azure Table Storage**
- 📦 **Order processing via Azure Queue + Azure Functions**
- 🧾 **Payment proof uploads using Azure File Shares**
- 🖼️ **Product image storage using Azure Blob Storage**
- 🛠️ **Serverless functions for CRUD and queue processing**
- 🚀 **Deployment on Azure App Service (Windows)**

The system is designed to showcase real-world cloud integration using Microsoft Azure and follows the CLDV6212 POE Part 3 requirements.

---

## 🧱 System Architecture

### **1. ASP.NET Core MVC Web Application**
- Handles UI, authentication, dashboards, cart, and product browsing.
- Uses session-based login (Admin + Customer roles).

### **2. Azure SQL Database**
- Stores user accounts  
- Stores cart items  
- Stores authentication details  

### **3. Azure Storage Services**
- **Table Storage:** Products & Orders  
- **Blob Storage:** Product images  
- **File Share:** Payment proof documents  
- **Queue Storage:** Order messages for processing  

### **4. Azure Functions (.NET Isolated Worker)**
- `Orders_Enqueue` – HTTP Trigger (sends order to queue)  
- `Orders_Process` – Queue Trigger (creates/updates orders table)  
- `Orders_Finalize` – Queue Trigger  
- `ProductImage_Upload` – HTTP  
- `Contracts_SaveToFiles` – HTTP  
- Customer CRUD APIs  

### **5. Azure App Service (Windows)**
- Hosts & runs the production website  
- Fully linked to Azure SQL & Storage resources  

---

## ✔ Features

### **Customer Features**
- Register & log in (SQL)
- View products (Table Storage)
- Add items to cart (SQL)
- Checkout (via Azure Functions queue)
- Upload payment proof (File Share)
- View order history (Table Storage)

### **Admin Features**
- Manage products  
- Manage customers  
- View and update orders  
- View payment proofs  

---

## 📦 Technologies Used

| Technology | Purpose |
|-----------|---------|
| **ASP.NET Core MVC** | Web UI, routing, session authentication |
| **Azure SQL Database** | User accounts, cart storage |
| **Azure Functions** | Queue-triggered serverless order processing |
| **Azure Table Storage** | Product & order metadata |
| **Azure Blob Storage** | Product images |
| **Azure File Share** | Payment proof documents |
| **Azure Queue Storage** | Order pipeline messages |
| **Azure App Service** | Hosting and deployment |
| **Visual Studio 2022** | Development & publishing |
| **GitHub** | Version control & project hosting |

---

## ▶ How the Order Pipeline Works

1. Customer checks out cart  
2. MVC app sends order → **Orders_Enqueue** Function  
3. Function pushes order → **Azure Queue**  
4. **Orders_Process** Function triggers and writes to **Orders Table**  
5. Customer/Admin can view updated order status  

This architecture ensures scalability, durability, and reliable asynchronous processing.

---

## 📸 Required Evidence

All screenshots for the POE are included in the Word document submission:

- SQL Tables (Users, Cart)  
- Products in Table Storage  
- Orders Table  
- Blob images  
- Payment proofs File Share  
- Function App dashboard  
- Queue messages being processed  
- Frontend evidence (cart, orders, dashboards, etc.)  
- App Service publish & configuration  

---

## 🔐 Authentication

- SQL-based (no Identity framework)  
- Password hashing implemented  
- Sessions store:  
  - `UserName`  
  - `UserRole` (Customer/Admin)  

---

## 📜 Academic Integrity Note

Portions of this project (UI layout guidance, troubleshooting deployment issues, and explanatory text) were supported using **ChatGPT (OpenAI)**.  
All implementation logic, Azure configuration, architecture decisions, and source code were created by the student.

---

## 🧑‍💻 Author

**Riaad Hercules**  
2025

