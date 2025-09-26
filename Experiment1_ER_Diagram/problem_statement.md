# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:
<img width="1024" height="640" alt="image" src="https://github.com/user-attachments/assets/ac6ad8f6-2f54-4e5c-8338-e322b0ee1db6" />


### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
| :--- | :--- | :--- |
| **MEMBER** | **MemberID** (PK), Name, StartDate, **MembershipTypeID** (FK) | Tracks individual gym members. The foreign key links to the `MEMBERSHIP_TYPE` table for data consistency. |
| **MEMBERSHIP_TYPE** | **MembershipTypeID** (PK), TypeName, Fee, Duration | Defines the various membership plans available (e.g., Gold, Silver) and their associated costs and duration. |
| **PROGRAM** | **ProgramID** (PK), ProgramName, Description | Represents a specific fitness program, such as Yoga or Zumba. |
| **TRAINER** | **TrainerID** (PK), Name, Specialization | Stores information about each gym trainer and their area of expertise. |
| **PERSONAL_SESSION** | **SessionID** (PK), SessionDate, SessionTime, **MemberID** (FK), **TrainerID** (FK), Status | Details a one-on-one training session, linking the member and the trainer. |
| **PAYMENT** | **PaymentID** (PK), Amount, PaymentDate, **MemberID** (FK) | Records all financial transactions made by a member. |
| **ENROLLMENT** | **MemberID** (FK, PK), **ProgramID** (FK, PK), EnrollmentDate | A join table for the many-to-many relationship between `MEMBER` and `PROGRAM`, showing which members are enrolled in which programs. |
| **PROGRAM_TRAINER** | **ProgramID** (FK, PK), **TrainerID** (FK, PK) | A join table for the many-to-many relationship between `PROGRAM` and `TRAINER`, indicating which trainers are assigned to which programs. |
| **ATTENDANCE** | **SessionID** (FK, PK), **MemberID** (FK, PK), AttendanceStatus | Records a member's attendance for a specific session. |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
| :--- | :--- | :--- | :--- |
| Member ENROLLS IN Program | M:N | Partial (Member, Program) | Members can join multiple programs; programs have multiple members. |
| Trainer LEADS Program | M:N | Partial (Trainer), Partial (Program) | Trainers lead multiple programs; programs have multiple trainers. |
| Member BOOKS Personal_Session WITH Trainer | M:N | Partial (Member, Trainer), Total (Session) | Members book sessions with trainers; trainers conduct sessions. |
| Member MAKES Payment | 1:N | Total (Payment), Partial (Member) | Payments by a member; a member makes many payments. |
### Assumptions
-  Person can be either a Member, a Trainer, or potentially both
- A Member has one primary membership (with a type, fee, and start date) but can Enroll in multiple Programs.
- A Program is Led by one Trainer.

---

# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_library.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_restaurant.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
