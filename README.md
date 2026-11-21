# Medico Pharmacy

An online medical store where users browse and order healthcare products, built as my CDAC 2024 project. Spring Boot + MySQL REST API with JWT authentication and a React frontend.

[![Live demo](https://img.shields.io/badge/demo-live-brightgreen?logo=vercel)](https://medico-pharmacy.vercel.app)
![Java](https://img.shields.io/badge/Java-17-ED8B00?logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.0-6DB33F?logo=springboot&logoColor=white)
![Spring Security](https://img.shields.io/badge/Spring%20Security-JWT-6DB33F?logo=springsecurity&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-8-4479A1?logo=mysql&logoColor=white)
![React](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=black)
![Redux](https://img.shields.io/badge/Redux%20Toolkit-2-764ABC?logo=redux&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5-7952B3?logo=bootstrap&logoColor=white)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**Live demo:** https://medico-pharmacy.vercel.app

## About

I worked on the Medico project, an online medical store that allows users to browse and order healthcare products easily. For the backend, we used Spring Boot with MySQL to manage data and create secure REST APIs, while the frontend was built using React to ensure a smooth and responsive user experience.

My role involved setting up key backend features, like JWT-based authentication for secure login and role-based access control, so that admins and users had different access levels. I also helped design the MySQL database, organizing it with tables for users, products, orders, and carts. On the frontend, I integrated APIs to display products, manage the cart, and handle orders.

We followed an Agile workflow, using GitHub for version control and testing each part thoroughly. This project not only gave me hands-on experience with full-stack development but also taught me the value of teamwork, problem-solving, and building user-friendly applications.

## Features

**Customers**
- Register and log in (JWT-based authentication)
- Browse products by category, search by keyword, view product details
- Cart: add, update quantity and remove products
- Place orders and view order history in the user dashboard
- Manage delivery addresses

**Admins**
- Role-protected admin dashboard (`ADMIN` authority)
- Add, update and delete products (including product images) and categories
- View all orders and carts, update order status
- View and delete users

**API**
- REST endpoints under `/api` (public, user and `/api/admin` routes)
- Role-based access control with Spring Security
- Swagger UI / OpenAPI docs via springdoc

## Tech stack

| Layer    | Technologies |
|----------|--------------|
| Backend  | Java 17, Spring Boot 3.0, Spring Web, Spring Data JPA (Hibernate), Spring Security, java-jwt, ModelMapper, Lombok, springdoc-openapi |
| Database | MySQL |
| Frontend | React 18 (Create React App), React Router 6, Redux Toolkit, Axios, Bootstrap 5 / React-Bootstrap, react-hot-toast |

## Getting started

### Prerequisites
- JDK 17
- MySQL running locally
- Node.js and npm

### Backend (`Medico/`)

Database settings are read from environment variables (with local defaults) in `Medico/src/main/resources/application.properties`:
`DB_HOST`, `DB_PORT`, `DB_NAME` (default `ecommerceappdb`), `DB_USERNAME`.

Two secrets have no default and must be set before the app will start:
`DB_PASSWORD` (MySQL password) and `JWT_SECRET` (key used to sign login tokens; generate one with `openssl rand -base64 48`).
See [`Medico/.env.example`](Medico/.env.example).

```bash
cd Medico
cp .env.example .env   # then fill in DB_PASSWORD and JWT_SECRET
set -a; source .env; set +a
./mvnw spring-boot:run
```

The API starts on `http://localhost:8080`; Swagger UI is at `http://localhost:8080/swagger-ui/index.html`.

### Frontend (`my-app/my-app (copy)/`)

```bash
cd "my-app/my-app (copy)"
npm install
npm start          # http://localhost:3000
```

Sample category/product data is in `Products.sql` in the frontend folder.

## Project structure

```
Medico/                    Spring Boot backend
  src/main/java/com/app/
    config/                security, CORS and app config
    controllers/           REST controllers (auth, products, categories, cart, orders, users, addresses)
    entities/              JPA entities
    payloads/              DTOs
    repositories/          Spring Data repositories
    security/              JWT filter and utilities
    services/              business logic
my-app/my-app (copy)/      React frontend
html-css-pages/            early static HTML/CSS page mockups
Documentation/             project report, certificate and design docs
Project video.mp4          project demo video
```

## Documentation

- [Project report (PDF)](Documentation/project.pdf)
- [Purpose, scope and workflow (PDF)](Documentation/Purpose-scope-workflow.pdf)
- [Project demo video](Project%20video.mp4)
- Initial database design:

  ![Initial database design](Documentation/Screenshot%202024-05-03%20152957.png)

## License

Released under the [MIT License](LICENSE).
