# RaceDay POE - Part 1

## System Planning and Database

### GitHub Repository

https://github.com/MAANDA-M/RaceDay-POE-PART-1

---

## Project Overview

RaceDay is a race event management system designed to allow organisers to create and manage race events while participants can register, manage their profiles, view available events, enrol in event categories and view their race results.

This repository contains the planning and database components developed for Part 1 of the RaceDay Portfolio of Evidence (POE).

Part 1 focuses on planning the system before implementation by developing an Entity Relationship Diagram (ERD), an API Endpoint Plan and a SQL Server database script.

---

## Part 1 Deliverables

The following deliverables are included in Part 1:

- Entity Relationship Diagram (ERD)
- RESTful API Endpoint Plan
- SQL Server Database Script
- Realistic Sample Data
- GitHub Repository
- Minimum of 20 Meaningful GitHub Commits
- GitHub Actions CI/CD Validation
- Successful CI/CD Build Screenshot
- Unlisted YouTube Walkthrough Video

The planning documents and SQL database script are stored inside the `/docs` folder of this repository.

---

# User Roles

The RaceDay system contains two main user roles:

## Organiser

An Organiser is responsible for creating and managing race events.

An Organiser can:

- Log into the RaceDay system
- View their profile
- Update their profile
- Create race events
- View race events
- Update events they own
- Delete events they own
- Create categories for their events
- Update event categories
- Delete event categories
- View participants enrolled in events
- Manage event enrolments
- Record race results
- View race results

---

## Participant

A Participant is a user who participates in RaceDay events.

A Participant can:

- Register a RaceDay account
- Log into the system
- View their profile
- Update their profile
- View available race events
- View event details
- View categories belonging to an event
- Enrol in an event category
- View their enrolments
- Withdraw from an enrolment
- View race results

---

# Section A - Entity Relationship Diagram

The RaceDay database was designed as a relational database.

The Entity Relationship Diagram contains the entities, attributes, primary keys, foreign keys and relationships required by the RaceDay system.

The database contains the following six entities:

1. Role
2. User
3. Event
4. Category
5. Enrolment
6. Result

---

## Role Entity

The `Role` entity stores the roles available in the system.

The two main roles are:

- Organiser
- Participant

Each user is assigned a role.

---

## User Entity

The `User` entity stores registered RaceDay users.

The entity stores information such as:

- User ID
- Full Name
- Email
- Password Hash
- Password Salt
- Role ID
- Created Date

The Role ID is used as a foreign key to connect a user to a role.

---

## Event Entity

The `Event` entity stores information about race events.

Event information includes:

- Event ID
- Name
- Description
- Event Date
- Location
- Distance
- Event Type
- Organiser ID

Each event is associated with the Organiser who created it.

---

## Category Entity

The `Category` entity stores the different categories available for a race event.

Category information includes:

- Category ID
- Event ID
- Name
- Minimum Age
- Maximum Age
- Category Distance

Each category belongs to a specific event.

---

## Enrolment Entity

The `Enrolment` entity records participants who enrol in race events.

Enrolment information includes:

- Enrolment ID
- Participant ID
- Event ID
- Category ID
- Enrolment Date

The entity links a participant to an event and a selected category.

---

## Result Entity

The `Result` entity stores a participant's race result.

Result information includes:

- Result ID
- Enrolment ID
- Finish Time
- Finish Position
- Recorded Date

Each result is associated with an enrolment.

---

# Database Relationships

The RaceDay database contains the following main relationships:

- One Role can be assigned to many Users.
- One Organiser can organise many Events.
- One Event can contain many Categories.
- One Participant can have many Enrolments.
- One Event can have many Enrolments.
- One Category can be associated with many Enrolments.
- An Enrolment may have a Result once the participant has completed the event.

Primary keys and foreign keys are used to maintain referential integrity between the database tables.

---

# Section B - RESTful API Endpoint Plan

The RaceDay API Endpoint Plan documents the endpoints that the RaceDay system will expose.

Each endpoint is planned before implementation.

The endpoint plan contains the following information for each endpoint:

- HTTP Method
- Route
- Description
- Role Required
- Request Body
- Expected Response

The endpoint plan covers the following functional areas:

- Authentication
- User Profile
- Events
- Categories
- Event Enrolments
- Results

---

## Authentication Endpoints

Authentication endpoints are used to register and authenticate RaceDay users.

The planned authentication functionality includes:

- User registration
- User login
- JWT authentication
- Role-based authorisation

Registration and login are public endpoints.

Other protected endpoints require the user to be authenticated.

---

## User Profile Endpoints

User profile endpoints allow logged-in users to:

- View their profile
- Update their profile information

Authentication is required to access profile information.

---

## Event Endpoints

Event endpoints allow the RaceDay system to manage race events.

The planned functionality includes:

- View all events
- View a specific event
- Create an event
- Update an event
- Delete an event

Only Organisers are allowed to create, update or delete events.

---

## Category Endpoints

Category endpoints allow categories to be managed for race events.

The planned functionality includes:

- View event categories
- View a specific category
- Create a category
- Update a category
- Delete a category

Participants can view categories.

Organisers can manage categories belonging to their events.

---

## Event Enrolment Endpoints

Event enrolment endpoints allow Participants to enter race events.

The planned functionality includes:

- Enrol in an event category
- View enrolments
- Withdraw from an enrolment
- Allow Organisers to view participants enrolled in their events

---

## Result Endpoints

Result endpoints are used to manage race results.

The planned functionality includes:

- Record a participant's result
- View event results
- View the result of a specific enrolment

Results include information such as finish time and finish position.

---

# Section C - SQL Server Database Script

The RaceDay database is implemented using Microsoft SQL Server.

The SQL database script creates the complete RaceDay database schema.

The database contains the following tables:

- Role
- User
- Event
- Category
- Enrolment
- Result

The SQL database structure is designed to match the RaceDay Entity Relationship Diagram.

---

## Database Constraints

The RaceDay SQL script uses database constraints to maintain data integrity.

The script includes:

- PRIMARY KEY constraints
- FOREIGN KEY constraints
- NOT NULL constraints
- UNIQUE constraints
- CHECK constraints
- DEFAULT values where required

These constraints help prevent invalid or inconsistent data from being stored in the database.

---

## Sample Data

The SQL script includes realistic sample data that can be used to test the RaceDay database.

The sample data includes at minimum:

- 2 Organisers
- 2 Participants
- 3 Events
- Categories for the events
- Sample Enrolments
- Sample Results

The sample data demonstrates that the database relationships work correctly.

---

# Running the SQL Database Script

The RaceDay SQL database script can be executed using Microsoft SQL Server Management Studio (SSMS).

To run the database:

1. Open Microsoft SQL Server Management Studio.
2. Connect to a SQL Server instance.
3. Open the `RaceDay_Database_Script.sql` file.
4. Execute the entire SQL script.
5. Confirm that the RaceDay database is created.
6. Confirm that all required tables are created.
7. Confirm that the sample data is inserted successfully.
8. Run the verification queries at the bottom of the script.

The script should execute successfully without errors.

---

# Technologies and Tools Used

The following technologies and tools were used during Part 1:

- Microsoft SQL Server
- SQL Server Management Studio (SSMS)
- Draw.io / diagrams.net
- Microsoft Word
- Git
- GitHub
- GitHub Actions

---

# Repository Structure

```text
RaceDay-POE-PART-1/
│
├── docs/
│   ├── RaceDay_ERD.png
│   ├── RaceDay_API_Endpoint_Plan.pdf
│   └── RaceDay_Database_Script.sql
│
├── .github/
│   └── workflows/
│       └── validation.yml
│
└── README.md
```

---

## RaceDay ERD

The ERD shows:

- All database entities
- Entity attributes
- Primary keys
- Foreign keys
- Relationships
- Relationship cardinality

File:

`/docs/RaceDay_ERD.png`

---

## RaceDay API Endpoint Plan

The API Endpoint Plan contains all planned RaceDay API endpoints.

Every endpoint includes:

- HTTP Method
- Route
- Description
- Role Required
- Request Body
- Expected Response

File:

`/docs/RaceDay_API_Endpoint_Plan.pdf`

---

## RaceDay Database Script

The SQL Server script contains:

- Database creation
- Table creation
- Primary keys
- Foreign keys
- Database constraints
- Sample data
- Verification queries

File:

`/docs/RaceDay_Database_Script.sql`

---

# GitHub Version Control

GitHub is used to manage the RaceDay Part 1 project and maintain a record of project development.

The repository uses meaningful commits to document changes made throughout the development process.

A minimum of 20 meaningful commits will be completed using the student's own GitHub account.

---

# GitHub Actions CI/CD

GitHub Actions is used to validate the structure of the RaceDay repository.

The CI/CD workflow will check that the required Part 1 files and folders are available in the repository.

The workflow will verify the presence of important files such as:

- `/docs`
- RaceDay ERD
- API Endpoint Plan
- SQL Database Script
- README

---

# Video Demonstration

An unlisted YouTube video will be created to demonstrate and explain the RaceDay Part 1 work.

The video will include:

- Introduction to RaceDay
- Explanation of the two user roles
- Explanation of the ERD
- Explanation of database entities
- Explanation of relationships and cardinality
- Explanation of the API Endpoint Plan
- Explanation of the SQL Server database script
- Running the SQL database script in SSMS
- Demonstrating successful database creation
- Showing the GitHub repository
- Showing the successful GitHub Actions workflow

---

# Author

**Maanda M**

RaceDay Portfolio of Evidence - Part 1  
2026

---

