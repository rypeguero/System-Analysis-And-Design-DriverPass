<div align="center">

# DriverPass System Analysis & Design

**A complete software design blueprint for a cloud-based driver-training platform**

![Systems Analysis](https://img.shields.io/badge/Systems-Analysis-2563EB?style=for-the-badge)
![UML](https://img.shields.io/badge/UML-Modeling-7C3AED?style=for-the-badge)
![Cloud](https://img.shields.io/badge/Cloud-AWS%20%7C%20Azure-F59E0B?style=for-the-badge)
![Backend](https://img.shields.io/badge/Backend-Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

[Overview](#about-the-project) • [Requirements](#system-requirements) • [UML Design](#uml-design) • [Documents](#project-documents)

</div>

---

## About the Project

DriverPass is a proposed web platform designed to help students prepare for driving exams through **DMV-aligned practice tests, lesson scheduling, progress tracking, training packages, instructor feedback, payments, and administrative reporting**.

The project converts stakeholder needs into functional requirements, nonfunctional requirements, workflows, UML models, and a scalable technical architecture.

## Project Snapshot

| Area | Design Decision |
|---|---|
| Users | Students, instructors, administrators, secretaries, and DMV stakeholders |
| Platform | Responsive web application for desktop and mobile browsers |
| Backend | Python preferred, with Java as an alternative |
| Database | PostgreSQL or MySQL relational database |
| Hosting | AWS or Azure cloud infrastructure |
| Security | Role-based access, MFA for administrators, lockout after three failed attempts |
| Reliability | 99% uptime target, automated backups, monitoring, and disaster recovery |
| Performance | Under two seconds for exam submissions and scheduling updates |

## Core Capabilities

- Account creation, login, logout, and password recovery
- Role-based access for students, instructors, and administrators
- DMV-style practice quizzes with automatic grading
- Driving lesson scheduling, modification, and cancellation
- Training package selection, cart, checkout, and payment confirmation
- Student progress tracking and instructor comments
- Administrative user, package, policy, and report management
- Timestamped audit logs for reservation changes

## System Requirements

<details open>
<summary><strong>Functional requirements</strong></summary>

- Validate credentials and assign role-based permissions
- Allow students to schedule, modify, and cancel lessons
- Grade practice exams and store results
- Track training progress and instructor feedback
- Generate progress and activity reports
- Allow administrators to manage accounts, packages, and DMV updates

</details>

<details>
<summary><strong>Nonfunctional requirements</strong></summary>

- Compatible with Chrome, Firefox, Safari, and mobile devices
- Less than two seconds response time for key actions
- Cloud-hosted with scalable storage and processing
- Case-insensitive usernames and case-sensitive passwords
- Multi-factor authentication for administrators
- Account lockout after three failed login attempts
- Email or SMS password recovery
- Automated backups and real-time error alerts

</details>

<details>
<summary><strong>Assumptions and limitations</strong></summary>

**Assumptions**

- DMV policy updates can be integrated through an API
- A third-party provider such as Stripe processes card payments
- Users have reliable internet access

**Limitations**

- No offline scheduling or exam functionality
- Major package customizations require developer involvement

</details>

## UML Design

### Use Case Coverage

The system models interactions for students, instructors, administrators, secretaries, and DMV stakeholders across authentication, studying, testing, scheduling, purchasing, reporting, and policy management.

### Login and Registration Flow

```mermaid
flowchart TD
    A[Open DriverPass] --> B{Existing user?}
    B -->|Yes| C[Enter credentials]
    C --> D{Valid?}
    D -->|No| C
    D -->|Yes| E[Signed in]
    B -->|No| F[Create account]
    F --> G[Validate registration]
    G -->|Invalid| F
    G -->|Valid| H[Send confirmation]
    H --> E
```

### Package Purchase Flow

```mermaid
flowchart TD
    A[User logs in] --> B[Choose training package]
    B --> C[Add package to cart]
    C --> D[Checkout]
    D --> E[Enter card information]
    E --> F{Payment valid?}
    F -->|No| G[Display payment error]
    G --> E
    F -->|Yes| H[Process payment]
    H --> I[Send email and text confirmation]
```

### Main Domain Model

```mermaid
classDiagram
    User <|-- StudentDriver
    User <|-- Employee
    Employee <|-- Administrator
    Employee <|-- Instructor
    StudentDriver --> Schedule
    Schedule --> Appointment
    StudentDriver --> Test
    StudentDriver --> Cart
    Cart --> Package
    Cart --> Payment
    Instructor --> Appointment
    Administrator --> Report
```

## Technical Architecture

```mermaid
flowchart LR
    U[Web and Mobile Browser] --> F[JavaScript Frontend]
    F --> A[Python API]
    A --> DB[(PostgreSQL or MySQL)]
    A --> P[Payment Provider]
    A --> D[DMV Content Integration]
    A --> R[Reports and Audit Logs]
    DB --> B[Automated Backups]
    A --> C[AWS or Azure]
```

## Project Timeline

| Phase | Planned Window |
|---|---|
| Requirements collection | Late January to early February |
| Interface design | March |
| Database integration | Late March to early April |
| Login and security | April |
| Testing and delivery | Late April through May |

## Project Documents

| Document | View | Download |
|---|---|---|
| Business Requirements | [Open document](docs/DriverPass-Business-Requirements.md) | [Download](https://raw.githubusercontent.com/rypeguero/System-Analysis-And-Design-DriverPass/main/docs/DriverPass-Business-Requirements.md) |
| System Design and UML | [Open document](docs/DriverPass-System-Design.md) | [Download](https://raw.githubusercontent.com/rypeguero/System-Analysis-And-Design-DriverPass/main/docs/DriverPass-System-Design.md) |

## Skills Demonstrated

`Requirements Analysis` · `UML Modeling` · `Workflow Design` · `Object-Oriented Design` · `Cloud Architecture` · `Database Planning` · `Security Requirements` · `Technical Documentation`

---

<div align="center">

**Designed by Ryan A. Peguero**

</div>
