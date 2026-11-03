**Smart Tourist Safety Platform**



**Overview**



Smart Tourist Safety Platform is a full-stack web application designed to improve tourist safety by providing emergency assistance, location tracking, safety monitoring, and AI-based support.



The platform connects tourists, tour guides, and authorities to help make travel safer and more reliable.



**Features**



\- User authentication and authorization

\- Tourist dashboard

\- SOS emergency assistance

\- Live location tracking

\- Emergency contact management

\- Safety zones and geofencing

\- AI-powered assistant

\- Weather information

\- Tourist destinations

\- Authority dashboard

\- Tour guide module

\- Real-time updates



**Technology Stack**



**Frontend**

\- Next.js

\- React

\- TypeScript

\- Tailwind CSS



**Backend**

\- Java

\- Spring Boot

\- Spring Security

\- Spring Data JPA

\- REST APIs

\- WebSocket



**Database**

\- MySQL



**Tools**

\- Git and GitHub

\- VS Code

\- IntelliJ IDEA

\- Maven

\- Postman



**Project Structure**



SmartTouristSafetyPlatform/

├── backend/

│   ├── src/

│   ├── pom.xml

│   └── mvnw.cmd

├── frontend/

│   ├── src/

│   ├── public/

│   └── package.json

├── .gitignore

└── README.md

```



**Prerequisites**



\- Java JDK

\- Node.js and npm

\- MySQL

\- Git



**Setup and Installation**



**1. Clone the Repository**



git clone https://github.com/janvikhonde/SmartTouristSafetyPlatform.git

cd SmartTouristSafetyPlatform



**2. Create the Database**



CREATE DATABASE safetrail\_db;



Configure your database username and password in your local backend configuration file. Do not upload credentials to GitHub.



**3. Run the Backend**



cd backend

mvnw.cmd spring-boot:run



Backend URL: `http://localhost:8080`



**4. Run the Frontend**



Open another terminal:

cd frontend

npm install

npm run dev



Frontend URL: `http://localhost:3000`



**Application Architecture**



Tourists / Tour Guides / Authorities

&#x20;                 |

&#x20;                 v

&#x20;         Next.js Frontend

&#x20;            Port 3000

&#x20;                 |

&#x20;                 v

&#x20;         Spring Boot Backend

&#x20;            Port 8080

&#x20;                 |

&#x20;                 v

&#x20;             MySQL





**Purpose**



The main objective of this project is to provide a technology-based solution for tourist safety through emergency response, location-based services, real-time monitoring, and intelligent assistance.

