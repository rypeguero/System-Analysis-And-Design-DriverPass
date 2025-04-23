# DriverPass System Analysis And Design


This repository showcases my work on the DriverPass project, including the **Business Requirements Document** from my first project in this class and a **System Design Document** from the second project. Below is a summary of the project, reflections on my work, and insights into my design process.

---

## Project Summary
**Client**: DriverPass  
**Objective**: Design a web-based system to reduce driving test failures by providing students with online practice exams, on-road training scheduling, and centralized management for instructors and administrators.  
**Key Features**:
- Role-based access (students, instructors, admins).
- DMV-aligned practice exams with real-time grading.
- Scheduling system for driving lessons across three customizable packages.
- Activity logging, progress tracking, and automated reporting.
- Cloud-hosted infrastructure for scalability and reliability.

---

## Reflection

### 🏆 What I Did Well
- **Comprehensive UML Diagrams**: Created detailed use case, activity, sequence, and class diagrams to model system interactions, ensuring alignment with functional requirements.
- **Technology Selection**: Proposed a scalable cloud architecture (AWS/Azure), Python for backend logic, and MySQL for structured data management, balancing performance and development efficiency.
- **Clear Requirements Translation**: Mapped client goals (e.g., 40% failure rate reduction) to measurable technical tasks, such as real-time exam submissions (<2s response time).

### 🔄 Areas for Improvement
- **Class Diagram Refinement**: The initial class diagram had ambiguities (e.g., `static String` in the `USER` class). I would revise it to clarify attributes, fix data types (e.g., `city: Int` → `city: String`), and define relationships (e.g., aggregation between `Cart` and `Packages`).
- **Error Handling in Activity Diagrams**: The login sequence could better visualize error recovery paths (e.g., "Forgot Password" flow) to enhance user experience.

### 👥 User-Centric Design
- **Needs Interpretation**: Translated user pain points (e.g., 65% test failure rate) into features like adaptive practice quizzes and instructor feedback submission. Role-specific interfaces (student dashboards, admin tools) were prioritized to streamline workflows.
- **Importance of User Needs**: Ignoring user requirements risks building a technically sound but impractical system. For example, case-insensitive usernames and mobile-responsive design directly address accessibility and convenience.

### 🛠️ Design Approach
- **Model-Driven Development**: Leveraged UML diagrams to visualize system behavior and structure before implementation.
- **Modular Architecture**: Designed components (e.g., scheduling, payment) as independent modules for easier updates and scalability.
- **Future Strategies**: Incorporate user story mapping to prioritize features and adopt iterative development (e.g., Agile sprints) for continuous feedback.

## Thank you Reading!
