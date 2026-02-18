# 🏋️‍♂️ Fitness Microservice System

A modern, scalable fitness tracking application built with a **Microservices Architecture**. This system allows users to log workouts, manage profiles, and receive **AI-powered fitness recommendations** using Google's Gemini API.

---

## 🚀 Features

- **Microservices Architecture:** Decoupled services for User Management, Activity Tracking, and AI Analysis.
- **AI-Powered Insights:** Uses the **Gemini API** to analyze workout data and provide personalized suggestions, safety tips, and improvement plans.
- **Asynchronous Communication:** Uses **RabbitMQ** to handle data flow between the Activity and AI services.
- **Security:** Integrated with **Keycloak** for robust OAuth2 authentication and authorization.
- **Service Discovery & Config:** Built with **Spring Cloud Eureka** for service registration and **Spring Cloud Config** for centralized management.
- **Responsive Frontend:** A React-based Single Page Application (SPA) for a seamless user experience.

---

## 🏗️ Architecture Overview

The system consists of the following components:

1.  **User Service:** Manages user profiles and validation.
2.  **Activity Service:** Handles the logging and storage of fitness activities.
3.  **AI Service:** Consumes activity data via RabbitMQ and interfaces with the Gemini API for analysis.
4.  **Config Server:** Centralized configuration for all services.
5.  **Eureka Server:** Service discovery registry.
6.  **API Gateway:** (Optional/Recommended) Single entry point for the frontend.
7.  **Frontend:** React application for user interaction.

---

## 🛠️ Tech Stack

- **Backend:** Java 17+, Spring Boot 3.x, Spring Cloud
- **Frontend:** React, TypeScript, CSS3
- **Database:** PostgreSQL / MySQL (per service)
- **Messaging:** RabbitMQ
- **IAM:** Keycloak
- **AI Integration:** Google Gemini API
- **Containerization:** Docker

---

## 🚦 Getting Started

### Prerequisites
- **Java 17** or higher
- **Node.js & npm**
- **Docker** (for RabbitMQ and Keycloak)
- **Gemini API Key** (Get it from [Google AI Studio](https://aistudio.google.com/))

### 1. Clone the Repository

git clone [https://github.com/anshG2003/Fitness-Micro-Service.git](https://github.com/anshG2003/Fitness-Micro-Service.git)
cd Fitness-Micro-Service

### 2. Set Up Infrastructure
Run RabbitMQ and Keycloak using Docker:
docker run -d --name rabbitmq -p 5672:5672 -p 15672:15672 rabbitmq:3-management

### 3. Configuration
Update the application.yml in the AI Service with your Gemini API Key:
gemini:
  api:
    key: YOUR_GEMINI_API_KEY_HERE

### 4. Running the Services

Start the services in the following order:

Config Server
Eureka Server
User/Activity/AI Services
Frontend:

cd fitness-app-frontend
npm install
npm start

### 📝 License
This project is licensed under the MIT License - see the LICENSE file for details.

### 🤝 Contributing
Contributions are welcome! Please fork the repository and create a pull request for any improvements.
