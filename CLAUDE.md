# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Spring Boot 2.5.4 application using Java 8, built with Gradle. The project is currently in early stages with basic scaffolding in place.

**Group:** com.example
**Artifact:** demo
**Package:** com.example.demo

## Build and Test Commands

### Build the project
```bash
./gradlew build
```

### Run tests
```bash
./gradlew test
```

### Run a single test class
```bash
./gradlew test --tests com.example.demo.DemoApplicationTests
```

### Run a specific test method
```bash
./gradlew test --tests com.example.demo.ClassName.methodName
```

### Run the application
```bash
./gradlew bootRun
```

### Clean build artifacts
```bash
./gradlew clean
```

### Build without running tests
```bash
./gradlew build -x test
```

## Technology Stack

- **Java 8** - Configured via Gradle toolchain
- **Spring Boot 2.5.4** - Application framework
- **Spring Boot Starter Web** - REST API development
- **Spring Data JPA** - Database ORM
- **Spring Data Redis 2.5.1** - Redis integration
- **Oracle JDBC (ojdbc8 19.3.0.0)** - Oracle database driver
- **Lombok 1.18.20** - Reduces boilerplate code
- **JUnit 5** - Testing framework (via JUnit Platform Launcher)

## Project Structure

```
src/
├── main/
│   ├── java/com/example/demo/
│   │   └── DemoApplication.java       # Main Spring Boot application class
│   └── resources/
│       └── application.properties     # Application configuration
└── test/
    └── java/com/example/demo/
        └── DemoApplicationTests.java  # Basic integration test
```

## Development Notes

### Lombok Usage
- Lombok is configured as `compileOnly` and `annotationProcessor`
- IDE annotation processing must be enabled to work with Lombok annotations
- Common annotations: `@Data`, `@Builder`, `@Slf4j`, `@NoArgsConstructor`, `@AllArgsConstructor`

### Database Configuration
- Oracle JDBC driver is available for Oracle database connections
- JPA is configured but no entities or repositories exist yet
- Database connection details should be added to `application.properties` when implementing data layer

### Redis Configuration
- Spring Data Redis is available for caching or session management
- Redis connection details should be added to `application.properties` when implementing

## Architecture Guidelines

This is a standard Spring Boot application following the typical layered architecture pattern:
- **Controller Layer** - REST endpoints (not yet implemented)
- **Service Layer** - Business logic (not yet implemented)
- **Repository Layer** - Data access using Spring Data JPA (not yet implemented)
- **Entity/Model Layer** - Domain objects (not yet implemented)

When adding new features, follow the standard Spring Boot package structure:
- `com.example.demo.controller` - REST controllers
- `com.example.demo.service` - Business logic services
- `com.example.demo.repository` - Data repositories
- `com.example.demo.model` or `com.example.demo.entity` - Domain entities
- `com.example.demo.dto` - Data transfer objects
- `com.example.demo.config` - Configuration classes
