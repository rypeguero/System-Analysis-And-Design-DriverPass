# DriverPass System Design

## Design Summary

The DriverPass design models how students, instructors, administrators, secretaries, and DMV stakeholders interact with a cloud-hosted driver-training platform. The system combines user management, practice testing, lesson scheduling, package purchasing, reporting, and policy updates.

## UML Use Case Model

### Actors

- Student
- Instructor
- Administrator
- Secretary
- DMV

### Main Use Cases

- Create an account
- Log in and log out
- Reset a password
- View study materials
- Take practice quizzes
- Schedule or modify driving appointments
- Purchase training packages
- View training progress
- Manage users
- Disable training packages
- Update DMV policies and regulations
- Generate and view reports
- Assign instructors
- Submit driver comments
- Update student progress

## Login Activity Flow

1. The user opens the DriverPass website.
2. A returning user enters login credentials.
3. The system validates the credentials.
4. Invalid credentials return the user to the login step.
5. A new user selects registration and submits account information.
6. The system validates the registration information.
7. A successful registration produces a confirmation email or link.
8. The user signs in successfully.

## Package Purchase Activity Flow

1. The user logs in.
2. The user chooses a training package and adds it to the cart.
3. The user checks out.
4. The user enters credit or debit card information.
5. Invalid payment information produces an error message.
6. Valid payment information is processed.
7. The system sends a purchase confirmation.

## Purchase Sequence

The sequence diagram models communication among the student, driving package, DriverPass website, and payment system.

1. Student selects a package.
2. Package is added to the cart.
3. DriverPass displays the price.
4. Student proceeds to checkout.
5. DriverPass requests billing information.
6. Student submits payment details.
7. Payment failures return an error.
8. Corrected details are resubmitted when necessary.
9. The payment provider confirms a successful transaction.
10. DriverPass sends confirmation by text and email.

## Class Model

| Class | Responsibility |
|---|---|
| User | Stores account identity and authentication data |
| Owner/Administrator | Manages system-wide controls and reporting |
| Student Driver | Represents learners and their training records |
| Customer | Stores customer profile and address information |
| Employee | Represents DriverPass staff |
| Manager | Provides management-level access |
| Report | Stores generated report content and identifiers |
| Schedule | Organizes lessons and appointments |
| Appointment | Stores appointment details and notes |
| Test | Stores practice-test data and scores |
| Cart | Holds selected packages and total cost |
| Package | Defines package identity, name, and price |
| Payment | Represents purchase transactions |
| DMV Guide | Represents DMV-aligned study guidance |

## Technical Requirements

### Architecture

- Scalable, cloud-hosted web application
- Relational database for structured data and entity relationships
- Modular components for authentication, scheduling, testing, payments, and reporting

### Suggested Technology

- **Frontend:** JavaScript-based responsive web interface
- **Backend:** Python preferred for readability and development speed, with Java as another viable option
- **Database:** MySQL or PostgreSQL
- **Development environment:** Visual Studio Code
- **Version control:** Git and GitHub
- **Cloud hosting:** AWS or Azure

### Reliability and Recovery

- Automated routine backups
- Scalable compute and storage resources
- Disaster-recovery procedures
- Monitoring for availability and database failures

## Design Skills Demonstrated

- UML use case modeling
- Activity and workflow modeling
- Sequence modeling
- Object-oriented class modeling
- Requirements-to-design traceability
- Cloud architecture planning
- Database selection
- Security and recovery planning
