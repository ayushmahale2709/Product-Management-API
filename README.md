# Product Management API

## Overview
This project is a RESTful API for managing products using **Spring Boot** and **MongoDB**. The API supports CRUD (Create, Read, Update, Delete) operations and enables users to manage a collection of products efficiently. 

## Features
- Create, Read, Update, and Delete (CRUD) operations for products.
- MongoDB integration for persistent data storage.
- Validation and exception handling.
- Unit and integration testing.
- API testing using **Postman**.
- Demonstration via **MongoDB Compass** or **MongoDB shell**.

## Tech Stack
- **Spring Boot** (Backend Framework)
- **MongoDB** (Database)
- **Maven** (Dependency Management)
- **Postman** (API Testing)
- **MongoDB Compass** (Database Visualization)

## Project Structure
```
product-management-api/
│── src/
│   ├── main/
│   │   ├── java/com/example/productapi/
│   │   │   ├── controller/
│   │   │   ├── model/
│   │   │   ├── repository/
│   │   │   ├── service/
│   │   │   ├── exception/
│   ├── resources/
│   │   ├── application.properties
│── pom.xml
│── README.md
```

## Installation & Setup

### Prerequisites
- **Java 17+**
- **Spring Boot**
- **MongoDB (Local or Cloud)**
- **Postman**

### Steps to Run the Application
1. **Clone the Repository**
   ```sh
   git clone https://github.com/your-username/product-management-api.git
   cd product-management-api
   ```

2. **Configure MongoDB** (Update `application.properties` if needed)
   ```properties
   spring.data.mongodb.uri=mongodb://localhost:27017/productdb
   ```

3. **Build and Run**
   ```sh
   mvn clean install
   mvn spring-boot:run
   ```

## API Endpoints

### 1. Create Product
- **Endpoint:** `POST /api/products`
- **Request Body:**
   ```json
   {
     "name": "Wireless Mouse",
     "description": "Ergonomic wireless mouse with USB receiver",
     "price": 29.99,
     "quantity": 100,
     "category": "Electronics"
   }
   ```
- **Response:** Returns the created product with a unique `id`.

### 2. Retrieve All Products
- **Endpoint:** `GET /api/products`
- **Response:** Returns an array of products.

### 3. Retrieve Product by ID
- **Endpoint:** `GET /api/products/{id}`
- **Response:** Returns a single product object.

### 4. Update Product
- **Endpoint:** `PUT /api/products/{id}`
- **Request Body:**
   ```json
   {
     "price": 24.99,
     "quantity": 150
   }
   ```
- **Response:** Returns the updated product details.

### 5. Delete Product
- **Endpoint:** `DELETE /api/products/{id}`
- **Response:** A confirmation message indicating successful deletion.

## Testing with Postman
1. Import the provided **Postman collection**.
2. Run the API requests in order:
   - Create a product
   - Fetch all products
   - Retrieve product by ID
   - Update product details
   - Delete a product

## MongoDB Verification
1. **Using MongoDB Compass:**
   - Connect to the database.
   - Verify the `productdb` collection.
   - Check the data persistence.

2. **Using MongoDB Shell:**
   ```sh
   mongo
   use productdb
   db.products.find().pretty()
   ```

## Exception Handling
- **Invalid Product ID:** Returns `404 Not Found`.
- **Invalid Input Data:** Returns `400 Bad Request`.

## Testing Strategy
- **Unit Tests:** Test service and controller layers.
- **Integration Tests:** Validate end-to-end functionality.

## Video Demonstration
### video Link : [Demo Video](https://drive.google.com/file/d/12yE6ZG-6sw2WdhY6V3Qj4Szk7QsdQBUT/view?usp=sharing)


The demonstration video includes:
- Running the application.
- API testing in Postman.
- MongoDB data verification.
- Explanation of code structure.

## Challenges Faced & Solutions
- **Database Connection Issues** → Used correct MongoDB URI.
- **Validation Errors** → Implemented DTO and validation annotations.
- **Exception Handling** → Used `@ControllerAdvice` to handle errors.

## Conclusion
This API provides a structured approach to managing products, integrating with MongoDB, and following best practices for Spring Boot development.

---
**Author:** Ayush Mahale 
