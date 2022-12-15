# EduMicroServices 🎓

A comprehensive Student-Course Management System built with Spring Boot Microservices Architecture.

## 📋 Overview

EduMicroServices is a modern educational management platform that demonstrates microservices architecture using Spring Boot. The system manages students and courses with a distributed, scalable approach.

## 🏗️ Architecture

The project consists of 5 microservices:

- **🚪 API Gateway** (`microservice-gateway`) - Entry point for all requests (Port: 8080)
- **🔍 Service Discovery** (`microservice-eureka`) - Service registry and discovery
- **⚙️ Configuration Server** (`microservice-config`) - Centralized configuration management (Port: 8888)
- **👨‍🎓 Student Service** (`microservice-student`) - Student management (Port: 8090)
- **📚 Course Service** (`microservice-course`) - Course management (Port: 9090)

## 🛠️ Technologies Used

- **Spring Boot 3.1.4**
- **Spring Cloud Gateway** - API Gateway
- **Spring Cloud Netflix Eureka** - Service Discovery
- **Spring Cloud Config** - Configuration Management
- **Spring Data JPA** - Data persistence
- **OpenFeign** - Service-to-service communication
- **H2 Database** - In-memory database
- **Lombok** - Boilerplate code reduction
- **Maven** - Dependency management

## 📊 Data Model

### Student Entity
- ID, Name, Last Name, Email, Course ID

### Course Entity  
- ID, Name, Teacher

## 🚀 Getting Started

### Prerequisites
- Java 17+
- Maven 3.6+

### Running the Services

1. **Start Configuration Server**
   ```bash
   cd SpringMicroservices/microservice-config
   ./mvnw spring-boot:run
   ```

2. **Start Eureka Server**
   ```bash
   cd SpringMicroservices/microservice-eureka
   ./mvnw spring-boot:run
   ```

3. **Start Student Service**
   ```bash
   cd SpringMicroservices/microservice-student
   ./mvnw spring-boot:run
   ```

4. **Start Course Service**
   ```bash
   cd SpringMicroservices/microservice-course
   ./mvnw spring-boot:run
   ```

5. **Start API Gateway**
   ```bash
   cd SpringMicroservices/microservice-gateway
   ./mvnw spring-boot:run
   ```

## 📡 API Endpoints

### Through API Gateway (http://localhost:8080)

#### Students
- `GET /api/student/all` - Get all students
- `GET /api/student/search/{id}` - Get student by ID
- `POST /api/student/create` - Create new student
- `PUT /api/student/update/{id}` - Update student
- `DELETE /api/student/delete/{id}` - Delete student

#### Courses
- `GET /api/course/all` - Get all courses
- `GET /api/course/search/{id}` - Get course by ID
- `POST /api/course/create` - Create new course
- `PUT /api/course/update/{id}` - Update course
- `DELETE /api/course/delete/{id}` - Delete course

## 🔧 Configuration

The project uses Spring Cloud Config for centralized configuration management. Configuration files are located in:
- `microservice-config/src/main/resources/configurations/`

## 📁 Project Structure

```
SpringMicroservices/
├── microservice-config/     # Configuration Server
├── microservice-eureka/     # Service Discovery
├── microservice-gateway/    # API Gateway
├── microservice-student/    # Student Management Service
└── microservice-course/     # Course Management Service
```

## 🌟 Features

- **Microservices Architecture** - Scalable and maintainable
- **Service Discovery** - Automatic service registration and discovery
- **API Gateway** - Single entry point with routing
- **Centralized Configuration** - External configuration management
- **Inter-service Communication** - Using OpenFeign
- **Data Persistence** - JPA with H2 database
- **Load Balancing** - Built-in load balancing capabilities

## 🏃‍♂️ Quick Test

Once all services are running, you can test the system:

```bash
# Get all students
curl http://localhost:8080/api/student/all

# Get all courses  
curl http://localhost:8080/api/course/all
```

## 📝 Sample Data

The system comes with pre-loaded sample data:
- 5 students (Juan, María, Pedro, Ana, Carlos)
- 5 courses (Matemáticas, Historia, Ciencias, Literatura, Educación Física)

## 🧪 Testing

The project includes unit tests for all microservices. Run tests using:

```bash
# Run all tests
mvn test

# Run tests for specific microservice
cd SpringMicroservices/microservice-student
mvn test
```

## 🤝 Contributing

Feel free to contribute to this project by submitting issues or pull requests.

---

*Built with ❤️ using Spring Boot Microservices*
