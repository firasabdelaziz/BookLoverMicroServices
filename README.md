
# BookLover Microservices

Welcome to BookLover Microservices, a mono-repo microservices project built with Laravel. This project is designed to handle user, book, and social functionalities through independent microservices. The API Gateway serves as a single entry point, simplifying client communication, improving security, and enabling load balancing. The architecture is scalable, modular, and supports independent deployment of microservices.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Microservices](#microservices)
- [API Gateway](#api-gateway)
- [Configuration](#configuration)
- [Testing](#testing)
- [Contributing](#contributing)
- [License](#license)

## Overview

BookLover Microservices is a distributed system that breaks down the traditional monolithic application into smaller, independent services. This architecture provides several advantages, including:

- **Scalability:** Each microservice can be scaled independently, allowing for efficient resource utilization.
- **Modularity:** Microservices are independently deployable and maintainable, promoting a modular and organized codebase.
- **Security:** Microservices communicate through the API Gateway, enforcing a centralized point for security measures such as authentication and authorization.
- **Load Balancing:** The API Gateway handles incoming requests and distributes them to the appropriate microservices, ensuring load balancing and high availability.

## Features

- **User Microservice:** Manages user-related functionalities, including authentication and user profile management.
- **Book Microservice:** Handles book-related operations such as adding, updating, and retrieving book information.
- **Social Microservice:** Supports social interactions, including comments, likes, and user connections.

## Prerequisites

Before you begin, ensure you have the following:

- [Docker](https://www.docker.com/) installed
- [Docker Compose](https://docs.docker.com/compose/install/) installed
- Laravel development environment set up

## Getting Started

1. Clone the repository:

```bash
git clone https://github.com/firasabdelaziz/BookLoverMicroServices.git
cd BookLoverMicroServices
```

2. Build and run the services:

```bash
sh startMicroservices.sh
```

3. Access the services:

- API Gateway: http://localhost:8000
- User Microservice: http://localhost:8001
- Book Microservice: http://localhost:8002
- Social Microservice: http://localhost:8003

## Microservices

### User Microservice

- Manages user-related functionalities.
- **Endpoints:**
  - `/users`: Retrieve user information.
  - `/auth`: User authentication.

### Book Microservice

- Handles book-related operations.
- **Endpoints:**
  - `/books`: Retrieve book information.
  - `/books/add`: Add a new book.

### Social Microservice

- Supports social interactions.
- **Endpoints:**
  - `/comments`: Retrieve comments for a book.
  - `/likes`: Manage likes for a book.
  - `/connections`: Manage user connections.

## API Gateway

The API Gateway serves as the single entry point for client communication. It routes requests to the respective microservices based on the provided endpoint.

- **API Gateway Endpoint:** http://localhost:8000

## Software Architecture Visualization

The software architecture of BookLover Microservices is visualized using the Context, Containers, Components, and Code approach. This approach provides a comprehensive understanding of the system's architecture:

Context: Describes the external elements interacting with the system, such as users, external services, and other systems.

Containers: Identifies the high-level containers (e.g., microservices) and their interactions within the system.

Components: Breaks down each container into individual components, representing classes, modules, or packages.

Code: Represents the detailed code-level view, illustrating how components are implemented.

## Configuration

Adjust the configuration files in each microservice's directory (`userService`, `bookService`, `socialService`) to customize settings such as database connections, environment variables, and service ports.


## Contributing

If you'd like to contribute to this project, please follow the [CONTRIBUTING.md](CONTRIBUTING.md) guidelines.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---