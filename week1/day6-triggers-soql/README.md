# Day 6 – Triggers and SOQL

---

## 1. What is SOQL

SOQL (Salesforce Object Query Language) is used to retrieve data from Salesforce database objects.

It is used to query records stored in standard and custom objects.

### Example use cases
- Find all records from an object
- Retrieve filtered records using conditions
- Get related records using relationships

### Simple query ideas
- Find all records where status is active
- Find records created this month
- Find records related to a specific owner

SOQL is used for reading and retrieving data from Salesforce efficiently.

---

## 2. What is an Apex Trigger

An Apex Trigger is a piece of Apex code that runs automatically when a database event occurs.

### Trigger events include
- Before insert
- After insert
- Before update
- After update
- Before delete
- After delete

### Example use cases
- Automatically update related records
- Send notifications after record creation
- Enforce business rules before saving data

A trigger is used to automate backend logic when data changes occur.

---

## 3. Differences

### Flow vs Trigger

| Flow | Apex Trigger |
|------|--------------|
| No-code automation tool | Code-based automation |
| Used for simple business processes | Used for complex logic |
| Easy for admins | Preferred for developers |
| Limited flexibility | Full control over logic |

---

### Before Trigger vs After Trigger

| Before Trigger | After Trigger |
|----------------|--------------|
| Executes before saving data | Executes after saving data |
| Used to modify field values | Used to work with related records |
| Used for validation or default values | Used for creating or updating related records |

---

## 4. Trigger Use Cases (College Management System)

### 1. Student Registration
When a student registers, send a welcome email automatically.

Event: After insert on Student

---

### 2. Course Capacity Full
When a course reaches maximum capacity, notify the faculty.

Event: After insert or update on Course Enrollment

---

### 3. Attendance Below Threshold
When attendance drops below a defined limit, send a warning notification.

Event: After update on Attendance

---

### 4. Fee Validation
If fee is not paid, prevent enrollment.

Event: Before insert or update on Enrollment

---

### 5. Course Completion
When a course is completed, generate a certificate record.

Event: After update on Course

---

## 5. Query Examples (English Style)

### Students
- Find students enrolled in a specific course
- Find students with attendance below 75 percent
- Find students with pending fees

### Courses
- Find courses assigned to a faculty member
- Find courses that are full
- Find active courses this semester

### Faculty
- Find faculty handling multiple courses
- Find faculty assigned to a specific course
- Find faculty without any course assignment

---

## 6. Reflection

Enterprise systems react automatically to data changes because they need to handle large volumes of dynamic data efficiently.

Manual processing is not practical due to:
- Continuous data changes
- Need for real-time processing
- Risk of human error
- Requirement for consistent business rules across the system

Event-driven architecture ensures that business logic executes automatically when data changes occur, improving scalability, reliability, and performance.

---

## Summary

SOQL is used for querying data from Salesforce objects.
Apex Triggers are used to automatically execute logic when data changes.
Flows handle simple automation while triggers handle complex and scalable logic.
Enterprise systems rely on event-driven behavior to ensure real-time responses.
