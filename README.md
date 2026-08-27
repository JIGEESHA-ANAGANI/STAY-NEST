# STAY-NEST — Hotel Management System

**STAY-NEST** is a cloud-native, microservices-based hotel management web application designed to handle end-to-end hotel operational workflows including reservations, room management, housekeeping, front desk operations, and automated notifications.

---

## 🏗️ System Architecture

The project is structured using a Microservices Architecture, leveraging **Spring Cloud Netflix Eureka** for service discovery and an **API Gateway** for centralized routing and security.

### Core Microservices & Components

* **`staynest-eureka-server`**: Service discovery server allowing all microservices to register and locate each other dynamically.
* **`staynest-api-gateway`**: Entry point for all client requests; handles routing, authentication propagation, and rate limiting.
* **`iam-service`**: Identity and Access Management; handles user authentication, registration, JWT issuance, and role-based authorization (Admin, Staff, Guest).
* **`reservation-service`**: Manages guest bookings, room availability checks, pricing, and reservation lifecycles.
* **`room-service`**: Manages room categories, individual room statuses, inventory, and amenities.
* **`frontdesk-service`**: Facilitates guest check-ins, check-outs, bill generation, and front desk operations.
* **`housekeeping-service`**: Tracks room cleaning schedules, maintenance requests, and staff assignments.
* **`fb-service`**: Food & Beverage service for handling room service orders, restaurant bookings, and dining billing.
* **`notification-service`**: Dispatches transactional alerts, SMS, and email notifications (booking confirmations, payment receipts).
* **`frontend`**: Single Page Application (SPA) user interface for guests and hotel staff.

---

## 🛠️ Tech Stack

* **Backend**: Java / Spring Boot, Spring Cloud (Gateway, Eureka)
* **Frontend**: HTML5, CSS3, JavaScript / React (or preferred framework)
* **Database**: PostgreSQL / MySQL (per-service or shared database)
* **Communication**: REST APIs, OpenFeign / RestTemplate
* **Security**: JWT (JSON Web Tokens), Spring Security

---

## 🚀 Getting Started

### Prerequisites

* **Java JDK**: 17 or higher
* **Build Tool**: Maven / Gradle
* **Node.js & npm**: (For frontend development)
* **Database**: MySQL / PostgreSQL

### Running Locally

1. **Clone the repository**:
   ```bash
   git clone [https://github.com/JIGEESHA-ANAGANI/STAY-NEST.git](https://github.com/JIGEESHA-ANAGANI/STAY-NEST.git)
   cd STAY-NEST
2. **Start Discovery Server**:
   ```bash
   cd staynest-eureka-server
   ./mvnw spring-boot:run
3. **Start API Gateway**:
   ```bash
   cd ../staynest-api-gateway
   ./mvnw spring-boot:run

4.**Start Microservices**:
   Run `iam-service`, `room-service`, `reservation-service`, and remaining services in any order:
   ```bash
   cd ../iam-service
   ./mvnw spring-boot:run



## 🔐 Key Features

* **Multi-Role Access Control**: Separate capabilities and access for Guests, Front Desk Staff, Housekeeping, and Admins.
* **Dynamic Booking System**: Real-time room allocation, status tracking, and pricing validation.
* **Housekeeping Tracking**: Real-time updates on room cleaning schedules and maintenance readiness.
* **Integrated F&B Operations**: Handles room service orders and dining billing linked with guest accounts.
* **Automated Notifications**: Transactional alerts and email/SMS updates for bookings and status changes.
