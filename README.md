# SpringMVCWeb - Spring Boot Online Library System

A modern Spring Boot REST API application for managing an online library system.

## Project Overview

This is a demo Spring Boot application showcasing RESTful API development with the following features:
- Book management (CRUD operations)
- Library inventory tracking
- Author-based book filtering
- Search functionality

## Tech Stack

- **Framework:** Spring Boot 3.5.11
- **Language:** Java 17
- **Build Tool:** Maven
- **Server:** Apache Tomcat (embedded)
- **API Type:** RESTful Web Services

## Project Structure

```
SpringMVCWeb/
├── src/
│   ├── main/
│   │   ├── java/com/klu/
│   │   │   ├── SpringMvcWebApplication.java     (Main Application Class)
│   │   │   ├── controller/
│   │   │   │   └── LibraryController.java       (REST Controller)
│   │   │   └── model/
│   │   │       └── Book.java                    (Data Model)
│   │   └── resources/
│   │       ├── application.properties
│   │       ├── static/
│   │       └── templates/
│   └── test/
│       └── java/com/klu/SpringMVCWeb/
│           └── SpringMvcWebApplicationTests.java
├── pom.xml                                       (Maven Configuration)
└── README.md                                     (This file)
```

## Package Structure

| Component | Package |
|-----------|---------|
| Main Application | `com.klu` |
| Model Classes | `com.klu.model` |
| Controllers | `com.klu.controller` |

## Getting Started

### Prerequisites

- Java Development Kit (JDK) 17 or higher
- Maven 3.6 or higher
- Git

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/kl2400032185/git-skill6.git
   cd SpringMVCWeb
   ```

2. **Build the project:**
   ```bash
   mvn clean package
   ```

3. **Run the application:**
   ```bash
   mvn spring-boot:run
   ```

   Or run the JAR file:
   ```bash
   java -jar target/SpringMVCWeb-0.0.1-SNAPSHOT.jar
   ```

4. **Access the application:**
   - Server runs on: `http://localhost:8080`

## API Endpoints

### Base URL
```
http://localhost:8080
```

### Available Endpoints

#### 1. Welcome Endpoint
```
GET /welcome
Response: "Welcome to Online Library System"
```

#### 2. Book Count
```
GET /count
Response: 100
```

#### 3. Book Price
```
GET /price
Response: 499.99
```

#### 4. Get All Books
```
GET /books
Response: ["Java Programming", "Spring Boot Guide", "Data Structures"]
```

#### 5. Get Book by ID
```
GET /books/{id}
Example: GET /books/1
Response: "Details of Book with ID: 1"
```

#### 6. Search Books
```
GET /search?title={title}
Example: GET /search?title=Java
Response: "Searching for book: Java"
```

#### 7. Get Books by Author
```
GET /author/{name}
Example: GET /author/John
Response: "Books written by Author: John"
```

#### 8. Add New Book
```
POST /addbook
Content-Type: application/json

Request Body:
{
  "id": 1,
  "title": "Spring Boot Guide",
  "author": "John Doe",
  "price": 299.99
}

Response: "Book added successfully!"
```

#### 9. View All Added Books
```
GET /viewbooks
Response: [
  {
    "id": 1,
    "title": "Spring Boot Guide",
    "author": "John Doe",
    "price": 299.99
  }
]
```

## Model Classes

### Book Model
The `Book` class represents a book entity with the following attributes:

| Attribute | Type | Description |
|-----------|------|-------------|
| id | int | Unique book identifier |
| title | String | Title of the book |
| author | String | Author of the book |
| price | double | Price of the book |

**Methods:**
- Constructor (default and parameterized)
- Getters and Setters for all attributes

## Testing with Postman

1. **Import Collection:** Create a new collection in Postman
2. **Test Endpoints:** Use the endpoints listed above
3. **Send Requests:** Test various HTTP methods (GET, POST)

### Sample Test Cases

**Test 1: Welcome Endpoint**
- Method: GET
- URL: `http://localhost:8080/welcome`
- Expected Status: 200

**Test 2: Add Book**
- Method: POST
- URL: `http://localhost:8080/addbook`
- Headers: `Content-Type: application/json`
- Body:
  ```json
  {
    "id": 101,
    "title": "Advanced Java",
    "author": "Jane Smith",
    "price": 399.99
  }
  ```
- Expected Status: 200

**Test 3: View All Books**
- Method: GET
- URL: `http://localhost:8080/viewbooks`
- Expected Status: 200

## Dependencies

### Spring Boot Starters
- `spring-boot-starter-web` - For building web and REST applications
- `spring-boot-starter-test` - For testing support

### Maven Plugins
- `spring-boot-maven-plugin` - For building and running Spring Boot applications

## Configuration

Default application properties are configured in `src/main/resources/application.properties`

### Server Configuration
- **Port:** 8080
- **Servlet Context Path:** / (root)

## Development

### Adding New Controllers
1. Create a new controller class in `com.klu.controller` package
2. Annotate with `@RestController`
3. Define request mapping methods

### Adding New Models
1. Create a new model class in `com.klu.model` package
2. Define attributes and getter/setter methods

## Build & Deployment

### Building the Application
```bash
mvn clean package
```

### Running Tests
```bash
mvn test
```

### Building Docker Image (Optional)
```bash
mvn spring-boot:build-image
```

## Troubleshooting

### Port Already in Use
If port 8080 is already in use, change it in `application.properties`:
```properties
server.port=8081
```

### Maven Build Issues
```bash
mvn clean install -U
```

### Java Version Mismatch
Ensure JDK 17+ is installed:
```bash
java -version
```

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is open source and available under the MIT License.

## Author

KLU (Koneru Lakshmaiah Education Foundation)

## Contact

For more information or support, please visit: https://github.com/kl2400032185/git-skill6

## Changelog

### Version 0.0.1-SNAPSHOT
- Initial project setup
- REST Controller with 9 endpoints
- Book model with CRUD operations
- Maven configuration with Spring Boot 3.5.11
- Java 17 support

---

**Last Updated:** March 14, 2026
