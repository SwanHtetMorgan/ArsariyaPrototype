# Arsariya Learning Platform Prototype dataBase implementation 

## Features

The Arsariya Learning Platform is a comprehensive system designed to facilitate online learning. It comprises the following key components:

- **Administration**: This module oversees the day-to-day operations of the platform, ensuring smooth functioning.

- **Platform Services for Instructors**: Equips instructors with the necessary tools and services to create and manage their courses effectively.

- **Student Interface**: Provides students with the ability to enroll in courses, with a maximum limit of 5 courses per 2 weeks.

## Workflow

#### Every living form entities have to register and change their password . Only if they changed, their account will be activated

### Admin

- **Certificate Management**: Administrators can generate certificates for students upon course completion, serving as formal recognition.

- **Monthly Reporting**: Generates monthly reports detailing various platform metrics, including:
    - Student interests
    - Instructor activities
    - Overall platform statistics
- **Announcement**: Can announce related to platform including system update and upcoming course
- **Review Management***: Can analysis on the feedback review and apply to the report

### Instructor

- **Registration and Approval**: Instructors need to register and await approval to gain access to the platform's teaching tools.

- **Course Creation**: Instructors are empowered to create courses, with each course comprising a minimum of 10 chapters.

- **Quiz Development**: Instructors have the capability to design quizzes, allowing for the assessment of student comprehension after each chapter.
    Otherwise,he/ she can utilize the quiz service provided by the platform 
- **Announcement**: Instructors have the capability to send the notification related to their course
- **Assessment**:Instructors have the capability to perform assessment for the student both by implementing quiz service or their own questions


### Student 

- **Registration and Approval** Student need to register
- **CourseEnrollment** Student can enroll only 5 courses per 2 week. This is intended to enhance the study ability 
- **Certificate** Student can take out the certification for the reorganization for completion

<hr> 

## Project and ER diagram

## Packages and Components

### Administration

This package encompasses components related to administrative functions of the platform, including user management and system roles.

- **Admin**: Represents the administrator entity with attributes such as username, password, contact details, and system role.


### User

This package contains entities representing platform users, including students and instructors.
### Notes
    Student and Instructor share the state and behaviour . We can use only one table
    named "USER" .They can be differentiated by the role

- **Student**: Represents a student with attributes like username, password, contact details, courses enrolled, etc.
- **Instructor**: Represents an instructor with similar attributes as a student, along with courses taught.

### Content On Platform

This package includes components related to course content management, such as courses and chapters.

- **Courses**: Represents a course entity with attributes like name, description, instructor ID, etc.
- **Chapter**: Represents a chapter within a course, including title, content, and completion percentage.

### Tracking Tool

This package contains components related to tracking user progress and course pathways.

- **PATHWAY**: Represents a pathway entity with categories and associated courses.
- **Progress**: Tracks user progress within courses, including completion percentages and pathways.

### Utilities

This package includes utility components like announcements, certificates, and reports.

- **Announcement**: Represents an announcement entity with title, description, and creator details.
- **Certificate**: Represents a certificate entity with content and creation date.
- **Report**: Represents a report entity with graphical data for platform analytics.

### User Request

This package includes components related to user feedback and requests.

- **Review**: Represents a review entity with description and star rating.
- **Request**: Represents a request entity with description.

### Enum

This package contains enumeration types for roles and status.

- **Role**: Enumerates system roles (ADMIN, INSTRUCTOR, STUDENT).
- **ActiveORINActive**: Enumerates status (ACTIVE, INACTIVE).

### Assessment

This package deals with assessment-related functionalities like quizzes and assignments.

- **Quiz**: Represents a quiz entity containing questions for assessment.
- **Assignment**: Represents an assignment entity with details like student ID and file path.

### Service For Course

This package includes components related to course content creation, such as questions for quizzes.

- **Question**: Represents a question entity with title, options, and correct answer.

## Relationships

**Mapping**:
- They both can contain List of courses.
- @OneToMany for the Students, Instructor and Quiz 
- @ManyToOne for Courses,Question 

## Table
 
Total sixteen, 
### AUTHOR

- SWAN HTET AUNG PHYO(Morgan)
