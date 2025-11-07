# E-commerce Backend - Spring Boot

Spring Boot backend for the E-commerce application with JWT authentication.

## 🚀 Quick Start

### Local Development
```bash
# Build the project
./mvnw clean package

# Run locally
./mvnw spring-boot:run
```

### Docker Build & Run
```bash
# Build Docker image
docker build -t ecommerce-backend .

# Run container
docker run -d \
  -p 8080:8080 \
  -e SPRING_DATASOURCE_URL="jdbc:mysql://host.docker.internal:3306/ecommerce" \
  -e SPRING_DATASOURCE_USERNAME="root" \
  -e SPRING_DATASOURCE_PASSWORD="password" \
  --name ecommerce-backend \
  ecommerce-backend
```

## 📋 Environment Variables

| Variable | Description | Example |
|----------|-------------|---------|
| `SPRING_DATASOURCE_URL` | MySQL database URL | `jdbc:mysql://localhost:3306/ecommerce` |
| `SPRING_DATASOURCE_USERNAME` | Database username | `root` |
| `SPRING_DATASOURCE_PASSWORD` | Database password | `password` |

## 🏗️ Architecture

- **Framework**: Spring Boot 2.7.18
- **Language**: Java 17
- **Build Tool**: Maven 3.9.6
- **Database**: MySQL 8.0
- **Authentication**: JWT (JSON Web Tokens)
- **Packaging**: WAR (deployed on Tomcat)

## 📁 Project Structure

```
src/
├── main/
│   ├── java/com/klu/ecommerce/
│   │   ├── controller/       # REST API endpoints
│   │   ├── entity/           # JPA entities
│   │   ├── repository/       # Data access layer
│   │   ├── security/         # Security & JWT
│   │   └── service/          # Business logic
│   └── resources/
│       └── application.properties
└── test/
```

## 🔒 API Endpoints

- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `GET /api/products` - Get all products
- `POST /api/products` - Create product (admin)
- And more...

## 🧪 Testing

```bash
# Run tests
./mvnw test

# Run with coverage
./mvnw test jacoco:report
```

## 📦 CI/CD

This project uses GitHub Actions for automated CI/CD. See `.github/workflows/ci-cd.yml` for pipeline configuration.

**Pipeline stages:**
1. Build and Test
2. Build & Push Docker Image
3. Deploy to AWS EC2

## 📚 Documentation

See [IMPLEMENTATION_GUIDE.md](../IMPLEMENTATION_GUIDE.md) for complete setup instructions.

## 🔧 Tech Stack

- Spring Boot
- Spring Security
- Spring Data JPA
- MySQL
- JWT
- Maven
- Docker
- Tomcat
