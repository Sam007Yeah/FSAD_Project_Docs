# 📐 System Architecture

The Collaborative Personal Scheduler is built on a robust, scalable architecture that leverages modern technologies for seamless collaboration, real-time updates, and secure data management.

---

## 🗂️ High-Level Overview

```mermaid
flowchart TB
    subgraph Frontend [Frontend: React.js]
        R1["React.js SPA"]
        R2["FullCalendar.js"]
        R3["Axios (REST API calls)"]
        R4["Socket.IO Client"]
        R5["Redux/Zustand"]
        R6["TailwindCSS / Material UI"]
    end

    subgraph Backend [Backend: Spring Boot]
        B1["REST Controllers"]
        B2["WebSocket Endpoints"]
        B3["Service Layer"]
        B4["Spring Security + JWT"]
        B5["Spring Data JPA (Hibernate)"]
        B6["Spring Mail"]
    end

    subgraph Database [Database]
        D1["PostgreSQL / MySQL"]
    end

    subgraph External [External Services]
        E1["SMTP Server (Gmail/SendGrid)"]
    end

    R3 --> B1
    R4 --> B2
    B5 --> D1
    B6 --> E1
    B3 --> B5
    B1 --> B3
    B2 --> B3
```

---

## 📝 Component Descriptions

### **Frontend**

- **React.js SPA:** Responsive single-page application for user interaction.
- **FullCalendar.js:** Interactive calendar interface.
- **Axios:** Handles RESTful API communication.
- **Socket.IO Client:** Enables real-time updates.
- **Redux/Zustand:** State management for UI and data.
- **TailwindCSS / Material UI:** Modern, accessible UI components.

### **Backend**

- **Spring Boot:** Core RESTful API and business logic.
- **REST Controllers:** Handle HTTP requests and responses.
- **WebSocket Endpoints:** Real-time event and calendar updates.
- **Service Layer:** Business logic and orchestration.
- **Spring Security + JWT:** Authentication and authorization.
- **Spring Data JPA (Hibernate):** ORM for database operations.
- **Spring Mail:** Automated email notifications.

### **Database**

- **PostgreSQL / MySQL:** Reliable, scalable relational data storage.

### **External Services**

- **SMTP Server (Gmail/SendGrid):** Email delivery for notifications and invitations.

---

## 🗒️ Notes

- **Scalability:** Modular design supports future feature expansion.
- **Security:** JWT-based authentication and role management.
- **Collaboration:** Real-time sync and notifications for seamless teamwork.

> For setup instructions, contribution guidelines, and API documentation, refer to the respective files in this
