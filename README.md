# ouple
# Shared Life Planner – Project Documentation

## 📘 Project Overview

A full-stack web application designed for couples to collaboratively manage their shared life — including tasks, goals, calendar events, and reminders. Each couple has their own private space in the app. The app is deployed and hosted by you and supports multiple couples using it concurrently.

---

## 🧱 Microservices Architecture

### 1. User Service

* Registers users
* Handles authentication (JWT)
* Supports couple linking (via invite code or approval)

### 2. Couple Service

* Manages couple data
* Links two users into a shared unit

### 3. Task Service

* Create, read, update, delete tasks
* Assign tasks to self or partner
* Couple-scoped tasks only

### 4. Goal Service

* Create and track shared/personal goals
* Progress tracking and milestone handling

### 5. Calendar Service

* Stores events and due dates
* Serves frontend-friendly calendar data

### 6. Reminder Service

* Handles scheduled reminders
* Sends email notifications for tasks/goals/events

### 7. API Gateway

* Unified entrypoint for frontend
* Routes requests to appropriate microservices
* Handles JWT validation

---

## 🔐 Security & Multi-Tenancy

* Every request includes a JWT token
* Each resource (task, goal, event) is scoped to a couple ID
* Access control enforced server-side on every API call

---

## 🌐 Frontend (Angular)

* Built with Angular 17+
* Uses Angular Router for navigation
* Uses Angular Material for UI components
* Features include:

  * Task board
  * Goal tracker
  * Calendar view
  * Reminder settings
  * Profile linking and management

---

## 🧪 Sample API Design

### POST /api/users/register

Registers a new user.

```json
{
  "email": "user@example.com",
  "password": "securePass123",
  "name": "Jane"
}
```

### POST /api/couples/invite

Invite a partner by email.

```json
{
  "inviteeEmail": "partner@example.com"
}
```

### POST /api/tasks

Create a new task for the couple.

```json
{
  "title": "Plan weekly groceries",
  "dueDate": "2025-05-10",
  "assignedTo": "partnerId",
  "priority": "High"
}
```

### GET /api/goals

Retrieve all goals for this couple.

### POST /api/reminders

Schedule a reminder.

```json
{
  "taskId": "abc123",
  "remindAt": "2025-05-09T18:00:00Z"
}
```

---

## 🚀 Deployment Plan

### Backend

* Deploy Spring Boot microservices using Fly.io, Railway, or Render
* Use Docker for containerization
* Use PostgreSQL for data storage

### Frontend

* Deploy Angular frontend to Vercel or Netlify

---

## 🧭 Project Milestones (10 Weeks)

### Week 1: Architecture & Auth Setup

**Goals:**

* Define microservices
* Set up Spring Boot and Angular
* Implement registration/login (JWT)
* Couple linking via invite or email approval

**Deliverables:**

* Login and couple linking working
* Basic project scaffolding

### Week 2: User & Couple Service

**Goals:**

* Build user and couple microservices
* Enforce couple context in services

**Deliverables:**

* User linking API
* Angular UI for invite/accept
* Couple ID scoped in JWT

### Week 3: Task Service

**Goals:**

* Build task CRUD APIs
* Couple-scoped task logic

**Deliverables:**

* Angular task board
* Add/edit/delete tasks

### Week 4: Goal Tracker

**Goals:**

* Build goal tracking service
* Add goal progress tracking

**Deliverables:**

* Angular goal UI with progress bar

### Week 5: Calendar Service

**Goals:**

* Event storage and listing
* Frontend calendar view (Angular Calendar)

**Deliverables:**

* Add/view calendar events
* Filter by task/goal/event

### Week 6: Reminder Service

**Goals:**

* Add reminder scheduler
* Email reminders for upcoming items

**Deliverables:**

* Reminder API
* Basic email notifications

### Week 7: Access Control & Security

**Goals:**

* Enforce data isolation between couples
* Secure frontend and backend routes

**Deliverables:**

* Tenant-isolated data access
* Frontend visibility scoped to couple

### Week 8: Deployment & Live Testing

**Goals:**

* Deploy frontend and backend
* Register test couples

**Deliverables:**

* Live functional app online

### Week 9: UI Polish & UX

**Goals:**

* Improve design with Angular Material
* Add mobile responsiveness

**Deliverables:**

* Polished UI
* Clean mobile experience

### Week 10: Finalization & Demo

**Goals:**

* Write documentation
* Record final demo

**Deliverables:**

* Demo-ready product
* Optional extras (waitlist, feedback form)

### Post-10 Week Stretch Ideas

* Real-time updates (WebSocket)
* Partner messaging/chat
* Firebase push notifications
* Journaling/memory tracking
* Habit builder
* Budget tracking
* Mobile wrapper (Ionic or React Native)

---

## 📄 README Scaffold

```md
# Shared Life Planner

A web app that helps couples collaborate on life together — tasks, goals, events, and reminders.

## Features
- Secure login and couple linking
- Shared and personal task manager
- Goal tracking with progress visualization
- Calendar with tasks and events
- Automated email reminders

## Tech Stack
- **Frontend**: Angular 17, Angular Material
- **Backend**: Spring Boot microservices (Java)
- **Database**: PostgreSQL
- **Deployment**: Fly.io, Vercel

## Getting Started
1. Clone backend and frontend repos
2. Set up `.env` files with secrets and DB info
3. Start each microservice via Docker or locally
4. Run Angular app with `ng serve`

## License
MIT
```

---

