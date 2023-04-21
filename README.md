# Fintech System

This is a microservice-based fintech system that provides a set of REST APIs for managing user accounts and transactions.

## Architecture

The system is designed using a microservice architecture, which allows for a scalable and flexible system. The system consists of the following microservices:

- __Accounts Service:__ Handles account creation, retrieval, and deletion.
- __Transactions Service:__ Handles transaction creation and retrieval.
- __Users Service:__ Handles user authentication and authorization.
- __Notifications Service:__ Sends notifications to users for account and transaction events.
- __Discovery Service:__ Provides service discovery and registration.
- __API Gateway:__ The API Gateway acts as a central entry point for accessing the microservices. It routes requests to the appropriate microservices and provides load balancing. Additionally, it can also handle cross-cutting concerns such as authentication and authorization using JSON Web Tokens (JWT).

The services are designed to be loosely coupled, allowing for independent deployment and scaling of each service. The services communicate with each other using REST APIs and are secured using JWT authentication.

In addition, the system uses an API Gateway to route requests to the appropriate microservice. The API Gateway is responsible for handling authentication and authorization, as well as load balancing and caching.

## Technologies

The system is built using the following technologies:

- Spring Boot: Provides a framework for building microservices with Java.
- Spring Security & JWT: Authentication and authorization.
- Spring Cloud Gateway: An API Gateway for routing requests.
- Eureka: A service discovery and registration server.
- Postgres: A relational database for data.
- Kafka: A message broker for sending notifications to users.
- Maven: A build automation tool used for managing dependencies and building the projects

## Getting Started

### Prerequisites
To run this project, you will need:

Java 17 or later
Apache Maven 3.6 or later.

### To get started with the system, follow these steps:

1. Clone these repositories and navigate to the project directory.

- [Users Service](https:// .com/Amy-Oji/users-microService)
- [Accounts Service](https://github.com/Amy-Oji/Account-MicroService) 
- [Transactions Service](https://github.com/Amy-Oji/Transactions-MicroService)
- [Notifications Service](https://github.com/Amy-Oji/NotificationMicroService)
- [Discovery Service](https://github.com/Amy-Oji/discovery-service)
- [API Gateway](https://github.com/Amy-Oji/api-gateway)

2. Start the Eureka server by running `mvn spring-boot:run` in the `discovery-server` directory.
3. Start the API Gateway by running `mvn spring-boot:run` in the `api-gateway` directory.
4. Start the Accounts service by running `mvn spring-boot:run` in the `accounts-service` directory.
5. Start the Transactions service by running `mvn spring-boot:run` in the `transactions-service` directory.
6. Start the Users service by running `mvn spring-boot:run` in the `users-service` directory.
7. Start the Notifications service by running `mvn spring-boot:run` in the `notifications-service` directory.

The services should now be running and registered with the Eureka server. You can access the APIs of each service through the API Gateway by sending requests to the following endpoints:

- Accounts Service: http://localhost:8085/api/v1/accounts
- Transactions Service: http://localhost:8085/api/v1/transactions
- Users Service: http://localhost:8085/api/v1/users, ***/auth
- Notifications Service: http://localhost:8085/api/v1/notifications

The API endpoints are secured using JWT authentication. To access the endpoints, you will need to first register via this endpoint:

`http://localhost:8085/api/v1/auth/register `

A JWT token would be generated and returned to you at registration. Copy the token and inclued it in the `Authorization` header of your subsequent requests.

## Known Issues
This system is still under development and may contain bugs and unfinished features.
Currently, the system is not dockerized, and it can only be tested on one's local machine.
There is no Swagger documentation available at the moment.

I am currnetly working to resolve these issues and improve the system.
