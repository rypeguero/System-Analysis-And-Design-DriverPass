# DriverPass Business Requirements

## Purpose

DriverPass is designed to reduce driving-test failures by giving students access to online practice exams and on-the-road training. The platform centralizes access for students, instructors, and administrators so they can manage schedules, monitor progress, and keep training content aligned with DMV regulations.

## System Background

DriverPass addresses the problem of students failing driving tests because they lack adequate preparation tools.

### Core Components

- Role-based authentication for students, instructors, and administrators
- Online practice-exam modules with real-time grading and DMV-aligned content
- Scheduling for driving lessons across three training packages
- Activity logging for reservations, cancellations, and modifications
- Progress tracking and instructor feedback
- Administrative controls and reporting

## Objectives and Goals

- Reduce exam failure rates by 40% within one year
- Maintain 99% system uptime
- Allow administrators to disable outdated training packages without developer intervention
- Provide responsive access through desktop and mobile browsers

## Nonfunctional Requirements

### Performance

- Web-based platform compatible with Chrome, Firefox, Safari, and mobile devices
- Less than two seconds response time for exam submissions and scheduling updates

### Platform Constraints

- Cloud hosting through AWS or Azure
- Relational database such as PostgreSQL for user data, exam results, lesson schedules, and activity logs
- Automated backups and scalable infrastructure

### Accuracy and Precision

- Usernames are case-insensitive
- Passwords are case-sensitive
- Reservation modifications must be recorded with timestamps and user IDs
- Administrators receive real-time alerts for critical system errors

### Adaptability

- Administrators can enable or disable training packages from a dashboard
- Modular architecture supports future DMV policy and exam-content updates
- Cloud infrastructure scales during periods of high demand

### Security

- Multi-factor authentication for administrator accounts
- Account lockout after three failed login attempts
- Password reset through email or SMS
- Secure communication between the client and server
- Role-based authorization

## Functional Requirements

- The system shall validate user credentials and assign role-based permissions.
- The system shall allow students to schedule, modify, or cancel driving lessons.
- The system shall provide practice exams with automatic grading.
- The system shall track student progress and instructor comments.
- The system shall generate PDF progress reports for instructors and administrators.
- The system shall allow administrators to manage accounts, packages, policies, and activity reports.
- The system shall allow instructors to update student progress and submit driver comments.

## User Interface Requirements

### Students

- View exam history
- View and manage scheduled lessons
- Select pickup and drop-off locations
- Purchase training packages
- Track training progress
- Use the platform from mobile or desktop browsers

### Instructors

- Submit session notes and driver comments
- Review student performance
- Update progress records
- View assigned appointments

### Administrators

- Manage user accounts
- Disable outdated training packages
- Monitor activity logs
- Update DMV policies and regulations
- Generate reports

## Assumptions

- DMV policy updates will be available through API integration
- A third-party payment provider such as Stripe will process card payments
- Users will have reliable internet access

## Limitations

- No offline scheduling or exam functionality
- Major package customizations, such as adding VR training, require developer work

## Project Schedule

| Phase | Planned Window |
|---|---|
| Collect requirements | Late January to early February |
| Build interface | March |
| Link database to interface | Late March to early April |
| Implement login security | April |
| Testing and delivery | Late April through May |

## References

- Valacich, J., & George, J. (2025). *Modern Systems Analysis and Design* (10th ed.). Pearson.
- Satzinger, J. W., Jackson, R. B., & Burd, S. D. (2023). *Systems Analysis and Design in a Changing World* (8th ed.). Cengage Learning.
