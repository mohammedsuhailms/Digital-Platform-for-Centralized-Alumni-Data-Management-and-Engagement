**1.PROJECT TITTLE**:**Digital-Platform-for-Centralized-Alumni-Data-Management-and-Engagement**:
**2.PROBLEM STATEMENT**:Many educational institutions face challenges in maintaining alumni records and fostering continuous engagement with former students. Alumni information is often scattered across multiple sources, making it difficult to track career progress, organize events, share job opportunities, and facilitate mentorship programs. The absence of a centralized and efficient platform leads to poor communication, limited networking opportunities, and reduced alumni participation. Therefore, there is a need for a secure and scalable digital platform that centralizes alumni data management and enables effective interaction between alumni, students, and administrators to strengthen institutional relationships and community engagement.
**3.PROJECT OBJECTIVES**:The Digital Platform for Centralized Alumni Data Management and Engagement aims to create a unified and user-friendly system for managing alumni information and strengthening connections between alumni, students, and the institution. The platform provides secure profile management, alumni directory services, event coordination, job and internship opportunities, mentorship programs, and communication features to promote continuous engagement and collaboration within the alumni community. It enables administrators to efficiently manage data, organize activities, and generate insights through a centralized dashboard, thereby enhancing networking, career development, and institutional growth.
**4.Module List**:
| Module No | Module Name                   | Description                          |
| --------- | ----------------------------- | ------------------------------------ |
| 1         | Authentication Module         | Login, Registration, Password Reset  |
| 2         | Alumni Profile Management     | Store and update alumni details      |
| 3         | Alumni Directory              | Search and view alumni information   |
| 4         | Event Management              | Create and manage alumni events      |
| 5         | Job & Internship Portal       | Share career opportunities           |
| 6         | Mentorship Module             | Connect alumni with students         |
| 7         | Communication Module          | Send announcements and notifications |
| 8         | Donation & Fundraising Module | Manage contributions and campaigns   |
| 9         | Admin Dashboard               | Analytics and overall system control |
| 10        | Feedback Module               | Collect feedback from alumni         |
**5.CRUD APIs**:
| Method | API Endpoint         | Description    |
| ------ | -------------------- | -------------- |
| POST   | /api/register        | Register user  |
| POST   | /api/login           | User login     |
| POST   | /api/forgot-password | Reset password |
**ALUMINI APIs**:
| Method | API Endpoint     | Description      |
| ------ | ---------------- | ---------------- |
| GET    | /api/alumni      | Get all alumni   |
| GET    | /api/alumni/{id} | Get alumni by ID |
| POST   | /api/alumni      | Add alumni       |
| PUT    | /api/alumni/{id} | Update alumni    |
| DELETE | /api/alumni/{id} | Delete alumni    |
**EVENT APIs**:
| Method | API Endpoint     |
| ------ | ---------------- |
| GET    | /api/events      |
| POST   | /api/events      |
| PUT    | /api/events/{id} |
| DELETE | /api/events/{id} |
**JOB APIs**:
| Method | API Endpoint   |
| ------ | -------------- |
| GET    | /api/jobs      |
| POST   | /api/jobs      |
| PUT    | /api/jobs/{id} |
| DELETE | /api/jobs/{id} |
**FEEDBACK APIs**:
| Method | API Endpoint       |
| ------ | ------------------ |
| GET    | /api/feedback      |
| POST   | /api/feedback      |
| DELETE | /api/feedback/{id} |
   **6.TABLE LIST**:
1.Users
2.Alumni
3.Student
4.Events
5.Jobs
6.Mentorship
7.Notifications
8.Donations
9.Feedback
10.Admin
**7.ER-DIAGRAM**:
          USERS
            |
            |
       ----------------
       |              |
    ALUMNI         ADMIN
       |
 ------------------------
 |      |       |       |
EVENTS JOBS MENTORSHIP FEEDBACK
       |
NOTIFICATIONS
       |
DONATIONS
**8.SQL SCHEMA**:
**USER TABLE**:
CREATE TABLE Users (
    user_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100),
    email VARCHAR(100) UNIQUE,
    password VARCHAR(255),
    role VARCHAR(20)
);
**ALUMINI TABLE**:
CREATE TABLE Alumni (
    alumni_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    batch_year INT,
    department VARCHAR(50),
    company VARCHAR(100),
    designation VARCHAR(100),
    location VARCHAR(100),
    FOREIGN KEY (user_id)
    REFERENCES Users(user_id)
);
**EVENTS TABLE**:
CREATE TABLE Events (
    event_id INT PRIMARY KEY AUTO_INCREMENT,
    title VARCHAR(100),
    description TEXT,
    event_date DATE,
    venue VARCHAR(100)
);
**JOBs TABLE**:
CREATE TABLE Jobs (
    job_id INT PRIMARY KEY AUTO_INCREMENT,
    company_name VARCHAR(100),
    position VARCHAR(100),
    location VARCHAR(100),
    last_date DATE
);
**FEEDBACK TABLE**:
CREATE TABLE Feedback (
    feedback_id INT PRIMARY KEY AUTO_INCREMENT,
    user_id INT,
    comments TEXT,
    rating INT,
    FOREIGN KEY (user_id)
    REFERENCES Users(user_id)
);
**9.PAGE LAYOUTS**:
Public Pages:
 *Home Page
 *About Page
 *Contact Page
Authentication Pages:
 *Login Page
 *Registration Page
 *Forgot Password Page
Alumni Pages:
 *Dashboard
 *Profile Page
 *Alumni Directory
 *Event Page
 *Job Portal
 *Mentorship Page
 *Feedback Page
Admin Pages:
 *Admin Dashboard
 *User Management
 *Event Management
 *Job Management
 *Reports and Analytics
**10.UI SCREENS**:
Screen 1: Home Page-
 Components:
  *Navigation Bar
  *Hero Section
  *Statistics Section
  *Footer
Screen 2: Login Screen-
 Components:
  *Email Field
  *Password Field
  *Login Button
  *Forgot Password Link
Screen 3: Dashboard Screen-
 Components:
  *Sidebar
  *Top Navigation Bar
  *Cards
  *Recent Events
  *Job Opportunities
  *Notifications
Screen 4: Alumni Directory Screen-
 Components:
  *Search Bar
  *Filters
  *Alumni List
  *View Profile Button
Screen 5: Event Screen-
 Components:
  *Event Cards
  *Event Details
  *Register Button
Screen 6: Job Portal Screen-
 Components:
  *Job List
  *Company Details
  *Apply Button
**11.UI PROTOTYPE**:
   FIGMA PROTOTYPE STRUCTRE:
Home
│
├── Login
├── Register
├── Dashboard
│     ├── Profile
│     ├── Alumni Directory
│     ├── Events
│     ├── Jobs
│     ├── Mentorship
│     └── Feedback
│
└── Admin Dashboard
      ├── Users
      ├── Events
      ├── Jobs
      ├── Reports
      └── Notifications
**12.DESIGN APPROVAL**:
 *Design Tools
 *Figma
 *Canva
 *Draw.io
 *Design Process
 *Requirement Analysis
 *Wireframe Design
 *UI Mockup Creation
 *Prototype Development
 *Stakeholder Review
 *Design Approval
 *Frontend Development
 **13.REACT PROJECT SETUP**:
   CREATE PROJECT:
       npx create-react-app alumni-management-system
   INSTALL DEPENDENCIES:
       npm install react-router-dom
       npm install axios
       npm install bootstrap
       npm install react-bootstrap
       npm install react-icons
  FOLDER STRUCTRE:
       src
│
├── components
│     ├── Navbar
│     ├── Sidebar
│     ├── Footer
│     └── Cards
│
├── pages
│     ├── Home
│     ├── Login
│     ├── Register
│     ├── Dashboard
│     ├── Profile
│     ├── AlumniDirectory
│     ├── Events
│     ├── Jobs
│     ├── Mentorship
│     └── Feedback
│
├── services
│     ├── AuthService.js
│     ├── AlumniService.js
│     ├── EventService.js
│     └── JobService.js
│
├── assets
├── App.jsx
└── main.jsx
| Layer           | Technology      |
| --------------- | --------------- |
| Frontend        | React.js        |
| Backend         | Spring Boot     |
| Database        | MySQL           |
| API Testing     | Postman         |
| UI Design       | Figma           |
| Version Control | GitHub          |
| Authentication  | JWT             |
| Hosting         | Vercel / Render |

1. Login Module

The Login Module is used for secure authentication of users such as Alumni, Students, and Admin.

Features:
User login with email/username & password
Role-based access (Admin / Alumni / Student)
JWT or session-based authentication (if backend used)
Forgot password option (optional)
Secure login validation

2. Registration Module

This module allows new users to register in the platform.

Features:
Alumni registration form
Student registration form
Input validation (email, phone, batch, etc.)
Profile creation
Data stored in database
Fields Example:
Name
Email
Department
Batch Year
Company (for alumni)
Password

3. Dashboard UI

Dashboard is the main control center of the platform.

Features:
Total alumni count display
Active users stats
Job postings overview
Event updates
Navigation sidebar
Quick access cards
UI Sections:
Header (Profile + Notifications)
Sidebar (Modules navigation)
Main Content Area (Stats & Charts)

4. Forms Completed Module

This module handles all submitted forms in the system.

Features:
Alumni registration form submissions
Job posting forms
Event registration forms
Mentor request forms
Form validation status

5. Data Listing Module

This module displays stored data in structured table format.

Features:
Alumni list view
Search functionality
Filter by batch / department / company
Pagination support
Edit / Delete actions (Admin only)
UI Example:
Name	Batch	Department	Company

6. Frontend Review

Frontend part is designed for user-friendly experience.

Features:
Responsive UI (Mobile + Desktop)
Clean dashboard design
Reusable components
Form validation UI
Navigation system
Modern UI using React / Bootstrap / Tailwind
Technologies:
React.js
HTML5
CSS3
JavaScript
Bootstrap / Tailwind CSS

Backend Setup – Digital Platform for Centralized Alumni Data Management and Engagement
Overview

The backend of the Alumni Management Platform is developed using Spring Boot and follows a layered architecture to provide secure, scalable, and maintainable REST APIs. It handles user authentication, alumni data management, event handling, job postings, mentorship requests, and dashboard analytics.

Technology Stack
Java 17
Spring Boot
Spring Data JPA
Spring Web
MySQL Database
Maven
Hibernate
Postman (API Testing)
Backend Architecture
backend
│
├── controller
│     ├── AuthController.java
│     ├── AlumniController.java
│     ├── StudentController.java
│     ├── EventController.java
│     ├── JobController.java
│     └── MentorshipController.java
│
├── service
│     ├── AuthService.java
│     ├── AlumniService.java
│     ├── StudentService.java
│     ├── EventService.java
│     ├── JobService.java
│     └── MentorshipService.java
│
├── repository
│     ├── AlumniRepository.java
│     ├── StudentRepository.java
│     ├── EventRepository.java
│     ├── JobRepository.java
│     └── MentorshipRepository.java
│
├── entity
│     ├── Alumni.java
│     ├── Student.java
│     ├── Event.java
│     ├── Job.java
│     └── Mentorship.java
│
├── config
│     └── SecurityConfig.java
│
└── application.properties
Dependencies Used
Spring Boot Starter Web
Spring Boot Starter Data JPA
Spring Boot Starter Validation
Spring Boot Starter Security (Optional)
MySQL Connector
Lombok
Maven
Database Connectivity

The backend is connected to a MySQL database using Spring Data JPA and Hibernate for object-relational mapping.

application.properties
spring.datasource.url=jdbc:mysql://localhost:3306/alumni_management
spring.datasource.username=root
spring.datasource.password=root

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true

server.port=8080
REST API Modules
Authentication Module
Login API
Registration API
Alumni Module
Add Alumni
Update Alumni
Delete Alumni
View Alumni List
Student Module
Student Registration
Profile Management
Event Module
Create Event
Update Event
View Events
Job Module
Post Jobs
View Job Listings
Mentorship Module
Request Mentor
Assign Mentor
Layered Architecture
Controller Layer

Handles incoming HTTP requests and returns API responses.

Service Layer

Contains business logic and processes user requests.

Repository Layer

Interacts with the MySQL database using JPA repositories.

Entity Layer

Represents database tables as Java classes.

Configuration Layer

Manages security and application configuration.

API Testing

All REST APIs are tested using Postman to ensure proper request handling, response generation, and database integration.

Outcome

The backend provides a robust and scalable foundation for the Digital Platform for Centralized Alumni Data Management and Engagement, enabling efficient management of alumni records, events, jobs, mentorship programs, and communication through secure RESTful services.


# Project Report Structure

## Title Page

* Project Title
* Student Name
* Register Number
* Department
* College Name
* Academic Year

## Certificate

## Acknowledgement

## Abstract

## Table of Contents

## Chapter 1: Introduction

* Background
* Problem Statement
* Existing System
* Proposed System
* Objectives
* Scope
* Advantages

## Chapter 2: Literature Survey

* Existing Alumni Management Systems
* Research Analysis
* Gap Analysis
* Comparative Study

## Chapter 3: System Analysis

* Functional Requirements
* Non-Functional Requirements
* Feasibility Study
* Software Requirements
* Hardware Requirements

## Chapter 4: System Design

* Architecture Diagram
* ER Diagram
* EER Diagram
* UML Class Diagram
* Use Case Diagram
* Sequence Diagram
* Activity Diagram
* Data Flow Diagram (DFD Level 0 & 1)

## Chapter 5: Database Design

* Database Schema
* Table Structure
* Relationships
* Primary Keys
* Foreign Keys

## Chapter 6: Backend Development

* Spring Boot Setup
* Project Structure
* Entity Classes
* Repository Layer
* Service Layer
* Controller Layer
* REST APIs
* Authentication

## Chapter 7: Frontend Development

* React Project Setup
* Component Structure
* Routing
* Forms
* Dashboard UI
* Responsive Design

## Chapter 8: API Testing

* Postman Collection
* CRUD Testing
* Login Testing
* Validation Testing
* Results

## Chapter 9: Implementation

* Login Module
* Registration Module
* Dashboard
* Alumni Module
* Events
* Jobs
* Mentorship
* Reports

## Chapter 10: Results

* Screenshots
* Output Images
* Dashboard
* Working Modules

## Chapter 11: Advantages

* Centralized Data
* Better Alumni Engagement
* Easy Communication
* Secure Authentication
* Scalable Design

## Chapter 12: Future Enhancements

* AI Chatbot
* Mobile Application
* Resume Analyzer
* Recommendation System
* Email Notifications
* Cloud Deployment

## Conclusion

## References

## Appendix

* SQL Scripts
* API Endpoints
* GitHub Repository Link

