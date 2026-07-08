
# E-Commerce API
The E-Commerce-API is a comprehensive backend service for an online store called Dream Shops. Built using Java and Spring Boot, this RESTful API supports all core functionalities required to operate an e-commerce platform. The project is modularized into several key packages to organize the codebase clearly and efficiently. (The payment system is currently under development.)

## Features

- User registration & login with role-based access control  
- Product listing and management (CRUD)  
- Order creation and tracking  
- Secure authentication using Spring Security & JWT  
- Database integration with Spring Data JPA (MySQL)  
- Input validation and exception handling  

## Tech Stack

- **Language:** Java 17  
- **Frameworks:** Spring Boot, Spring Security, Spring Data JPA  
- **Database:** MySQL  
- **Build Tool:** Maven  
- **Other Tools:** Git, Postman, Lombok

## Authentication

This API uses JWT (JSON Web Token) for secure authentication. Access tokens are provided on login and must be included in the `Authorization` header for protected endpoints:

```
Authorization: Bearer <token>
```

## Project Structure

```
E-Commerce-API-main/
├── .gitattributes
├── .gitignore
├── README.md
├── mvnw
├── mvnw.cmd
├── pom.xml
├── .mvn/
│   └── wrapper/
│       └── maven-wrapper.properties
└── src/
    └── main/
        ├── java/
        │   └── com/
        │       └── abdullayev/
        │           └── demoshops/
        │               ├── DemoShopsApplication.java
        │               ├── controllers/           # REST API controllers
        │               ├── data/                  # Data initialization 
        │               ├── dto/                   # Data transfer objects 
        │               ├── enums/                 # Enums 
        │               ├── exceptions/            # Custom exceptions 
        │               ├── models/                # Entity models
        │               ├── repositories/          # Repositories 
        │               ├── requests/              # Request payload classes 
        │               ├── responses/             # Response payload classes 
        │               ├── security/              # Spring Security config & classes 
        │               └── services/              # Business logic services 
        └── resources/
            └── application.properties

```

# Project Functionality Overview
Core Functional Areas
1. Controllers - 
This layer exposes REST API endpoints to handle HTTP requests. The controllers manage product listings, user operations, orders, carts, categories, images, and authentication. Most controllers are fully implemented, providing secure and efficient interfaces for frontend consumption.

2. Services - 
The service layer contains business logic and orchestrates data flow between controllers and repositories. It ensures validation, transactional integrity, and complex operations, such as order processing and cart management, are handled properly. This layer is completely implemented.

3. Models - 
Entity classes represent database tables for users, products, orders, carts, categories, images, and roles. These models form the data foundation and include necessary JPA annotations.

4. Repositories - 
Spring Data JPA repositories provide CRUD operations and custom queries for all entities. All repositories are implemented.

5. DTOs (Data Transfer Objects) - 
DTOs facilitate data exchange between the client and server by abstracting entity details and controlling payload structure. This module is completed.

6. Requests and Responses - 
These packages contain classes that define the structure of API request bodies and response payloads respectively, improving code clarity and client communication. They are fully developed.

7. Exceptions - 
Custom exceptions handle specific error cases like entity not found, invalid input, or authentication errors. A global exception handler manages consistent API error responses.

8. Security - 
The security package configures Spring Security to enable authentication and authorization. It implements JWT token handling, password encoding, and role-based access control to secure the API endpoints. This module is completed.

9. Data Initialization - 
The data package includes scripts and classes for preloading sample data into the database during application startup. It also partially supports authentication data setup.

Summary
 - The E-Commerce-API project delivers a fully functional backend with clean architecture, supporting:
 - User registration, login, and role management
 - Product catalog management with categories and images
 - Shopping cart functionality with item management
 - Order processing and status tracking
 - Secure API access through JWT-based authentication and authorization



## Getting Started

1. **Clone the repository**
   ```bash
   git clone https://github.com/IamAbdullayev/E-Commerce-API.git
   cd E-Commerce-API
   ```

2. **Configure application properties**
   Set your MySQL credentials and JWT secret in `src/main/resources/application.properties`:
   ```properties
   spring.datasource.username=your_username
   spring.datasource.password=your_password
   jwt.secret=your_secret_key
   ```

3. **Build and run the app**
   ```bash
   ./mvnw spring-boot:run
   ```

4. **Test API with Postman or curl**

## Example Endpoints

- `POST /api/v1/auth/register` – Register a new user  
- `POST /api/v1/auth/login` – Authenticate user and receive JWT  
- `GET /api/v1/products` – Get list of all products  
- `POST /api/v1/orders` – Create a new order (authenticated)

## Author

**Ramazan Abdullayev**  
[GitHub](https://github.com/IamAbdullayev) · [LinkedIn](https://www.linkedin.com/in/ramazanabdu11ayev) · [Telegram](https://t.me/iamabdullayev)

---
