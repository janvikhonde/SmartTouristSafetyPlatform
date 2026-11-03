# 🛡️ Smart Tourist Safety Platform

## 📌 About the Project

The **Smart Tourist Safety Platform** is a full-stack web application designed to improve tourist safety through emergency assistance, location-based services, real-time monitoring, and intelligent support.

The platform connects tourists, tour guides, and authorities to help users access safety-related services and respond to emergencies more effectively.

## 🎯 Problem Statement

Tourists may face unexpected situations while travelling, such as medical emergencies, unsafe locations, difficulty finding nearby emergency services, or delays in getting assistance.

This project aims to provide a centralized platform where users can access safety-related information and emergency support.

## ✨ Key Features

### 🆘 1. SOS Emergency Assistance
- Allows tourists to request help during an emergency.
- Supports emergency communication and notifications.

### 📍 2. Location Tracking
- Uses location services to identify and share the tourist's location.
- Supports location-based safety features.

### 🗺️ 3. Maps and Nearby Emergency Services
- Displays relevant nearby locations using map services.
- Helps users locate emergency services and other useful places.

### 🛡️ 4. Safety Monitoring
- Supports safety-zone and geofencing functionality.
- Helps monitor location-based safety events.

### 🤖 5. AI Assistant
- Provides an assistant interface for tourist-related queries and guidance.

### 👤 6. User Authentication
- Supports user registration and login.
- Provides role-based access to platform features.

### 🧑‍✈️ 7. Tour Guide and Authority Modules
- Provides dedicated interfaces for tour guides and authorities.
- Supports coordination and safety monitoring.

### 🔔 8. Real-Time Updates
- Uses real-time communication features to update application information.

## 🛠️ Technology Stack

| Category | Technologies |
|---|---|
| Frontend | Next.js, React, TypeScript |
| Backend | Java, Spring Boot |
| Database | MySQL |
| Backend APIs | REST APIs |
| Real-Time Communication | WebSocket |
| Security | Spring Security |
| Data Access | Spring Data JPA, Hibernate |
| Version Control | Git, GitHub |
| Build Tool | Maven |

## 🏗️ System Architecture

The application follows a frontend-backend architecture. The Next.js frontend communicates with the Spring Boot backend through REST APIs. The backend handles application logic and database operations.

```text
       Tourists / Tour Guides / Authorities
                       |
                       v
              Next.js Frontend
                 Port 3000
                       |
                   REST APIs
                       |
                       v
              Spring Boot Backend
                 Port 8080
                  /        \
                 v          v
              MySQL    External Services
                       (Maps / Location)
                       |
                       v
                WebSocket Updates
```

## 📂 Project Structure

```text
SmartTouristSafetyPlatform/
│
├── backend/
│   ├── src/
│   ├── pom.xml
│   ├── mvnw
│   └── mvnw.cmd
│
├── frontend/
│   ├── src/
│   ├── public/
│   └── package.json
│
├── .gitignore
└── README.md
```

## ⚙️ Prerequisites

Install the following tools before running the project:

- Java JDK
- Node.js and npm
- MySQL
- Git

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/janvikhonde/SmartTouristSafetyPlatform.git
cd SmartTouristSafetyPlatform
```

### 2. Configure the Database

Start MySQL and create the database:

```sql
CREATE DATABASE safetrail_db;
```

Configure the backend database connection using your local configuration file. Set the appropriate database URL, username, and password.

**Note:** Do not upload database passwords, JWT secrets, or other sensitive credentials to GitHub.

### 3. Run the Backend

Open a terminal:

```cmd
cd backend
mvnw.cmd spring-boot:run
```

Backend URL:

`http://localhost:8080`

### 4. Run the Frontend

Open another terminal:

```cmd
cd frontend
npm install
npm run dev
```

Frontend URL:

`http://localhost:3000`

## 🔄 Application Workflow

1. A user opens the web application and logs in.
2. The user accesses the available tourist safety features.
3. The frontend sends requests to the Spring Boot backend.
4. The backend processes requests and interacts with the MySQL database or relevant external services.
5. Relevant information and updates are returned to the frontend.

## 🔮 Future Enhancements

- Enhance emergency response and notification workflows.
- Add more location-based safety features.
- Improve real-time monitoring and alerts.
- Extend support for additional emergency services.
- Improve the AI assistant's capabilities.
- Add more analytics and reporting features.
- Improve mobile responsiveness and accessibility.

## ⚠️ Note

Some features may depend on location permissions, external services, API availability, and correct backend configuration. Use the application's emergency features responsibly and contact local emergency services directly when immediate assistance is required.
