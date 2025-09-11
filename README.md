# Collaborative Personal Scheduler

A modern, full-stack web application for organizing daily tasks and events with a calendar-based interface. Designed for seamless collaboration—share events, view availability, and propose meet-ups in real time.

---

## 🚀 Overview

The **Collaborative Personal Scheduler** empowers users to efficiently manage their schedules while enabling teamwork. Unlike traditional planners, it focuses on collaborative features for groups, teams, and students.

---

## ✨ Key Features

- **Personal Scheduling:**  
  Create, update, and delete events with category support (work, personal, study).

- **Collaboration:**  
  Share events, propose meet-ups, and view others’ availability.

- **Email Notifications:**  
  Automated reminders and event invitations.

- **Real-Time Updates:**  
  Instant calendar sync via WebSockets.

---

## 📚 Project Scope

### 1. User Authentication & Authorization

- Secure registration, login, and logout (JWT-based)
- Role management (user, admin)

### 2. Personal Calendar

- Monthly, weekly, and daily views
- CRUD operations for events
- Event categorization and color-coding

### 3. Event Sharing & Collaboration

- Share events by username/email
- View shared events
- Propose and respond to meet-up time slots

### 4. Additional Scope

- **Email Notifications:**

  - Event reminders
  - Invitations for shared events
  - Updates on meet-up proposals

- **Real-Time Sync:**
  - WebSocket-powered updates for shared events and proposals
  - Live calendar refresh

---

## 📝 Functional Requirements

- **Authentication:**  
  User sign-up, login, logout, JWT validation

- **Calendar Management:**  
  Add, edit, delete, categorize, and color-code events; multiple calendar views

- **Collaboration:**  
  Invite users, accept/reject invitations, propose meet-ups

- **Notifications:**  
  Email reminders and event updates

- **Real-Time Sync:**  
  Push live updates to all connected users

---

## 🛠️ Technologies

| **Frontend**                                 | **Backend**                                            |
| -------------------------------------------- | ------------------------------------------------------ |
| React.js – Modern UI framework               | Spring Boot – RESTful API core                         |
| FullCalendar.js – Interactive calendar       | Spring Security + JWT – Authentication & authorization |
| Axios – API communication                    | Spring Data JPA (Hibernate) – ORM                      |
| Socket.io (React client) – Real-time updates | PostgreSQL – Relational database                       |
|                                              | Spring Mail – Email notifications                      |
|                                              | Spring WebSocket (STOMP) – Real-time communication     |

---

## 👥 Suitable For

- Students
- Teams
- Small groups planning activities, meetups, or project timelines

---

> For setup instructions, contribution guidelines, and API documentation, see the respective files in this
