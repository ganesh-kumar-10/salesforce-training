# Day 3 – Data Modeling

## 1. Difference Between App, Object, Record, and Field

### App
An App in Salesforce is a collection of tools, tabs, objects, and features grouped together for a specific purpose.

Example:
College Management App

---

### Object
An Object is like a database table that stores a particular type of information.

Examples:
- Student
- Faculty
- Course
- Department

---

### Record
A Record is a single entry inside an object.

Example:
Student Object → Record:
- Name: Sai Kumar
- Age: 20
- Course: DBMS

---

### Field
A Field stores a specific piece of information inside a record.

Examples:
- Student Name
- Email
- Age
- Course Name

---

# 2. Standard vs Custom Objects

## Standard Objects
Standard Objects are already provided by Salesforce.

Examples:
- Account
- Contact
- Opportunity
- Lead

These are commonly used for CRM purposes.

---

## Custom Objects
Custom Objects are created by users based on business needs.

Examples in this project:
- Student__c
- Faculty__c
- Course__c
- Department__c

These are created specifically for the College Management System.

---

# 3. College Data Model

## Objects
- Student
- Faculty
- Course
- Department

---

## Relationships

### Department → Faculty
One department can have many faculty members.

Lookup field created in:
- Faculty object

---

### Department → Course
One department can offer many courses.

Lookup field created in:
- Course object

---

### Faculty → Course
One faculty member can teach many courses.

Lookup field created in:
- Course object

---

### Course → Student
One course can contain many students.

Lookup field created in:
- Student object

---

# Diagram

```text
                 Department
                 /        \
                /          \
               /            \
        Faculty              Course
                                 \
                                  \
                                  Student
```

# Detailed Relationship Flow

```text
Department
   │
   ├──> Faculty
   │
   └──> Course
            │
            └──> Student

Faculty
   │
   └──> Course
```
---

# 4. Formula Fields

## 1. Full Name

### Formula
First_Name__c & " " & Last_Name__c

### Why Automatically Calculate?
- Saves time
- Avoids typing errors
- Creates consistent student names

---

## 2. Remaining Seats

### Formula
Total_Seats__c - Enrolled_Students__c

### Why Automatically Calculate?
- Shows live seat availability
- Prevents manual counting mistakes
- Helps students know available seats instantly

---

## 3. Percentage

### Formula
(Obtained_Marks__c / Total_Marks__c) * 100

### Why Automatically Calculate?
- Provides instant results
- Reduces manual calculation errors
- Useful for reports and grading

---

# 5. Validation Rules

## 1. Student Email Cannot Be Empty

### Formula
```salesforce
ISBLANK(Email__c)
```

### Error Message
```text
Email field cannot be empty.
```

### Problem Prevented
- Prevents records without contact information
- Ensures communication with students

---

## 2. Student Age Must Be Greater Than 0

### Formula
```salesforce
Age__c <= 0
```

### Error Message
```text
Student age must be greater than 0.
```

### Problem Prevented
- Prevents invalid age values
- Maintains accurate student data

---

## 3. Enrolled Students Cannot Exceed Total Seats

### Formula
```salesforce
Enrolled_Students__c > Total_Seats__c
```

### Error Message
```text
Enrolled students cannot exceed total course seats.
```

### Problem Prevented
- Prevents overbooking courses
- Maintains proper seat limits

---

# 6. Reflection – Why Structured Enterprise Data Matters

Structured enterprise data helps organizations store and manage information in an organized way.

Compared to random spreadsheets, structured systems:
- Reduce duplicate data
- Improve accuracy
- Make reporting easier
- Help teams collaborate efficiently
- Maintain relationships between records

In a College Management System, structured data connects students, faculty, courses, and departments properly. This makes the system more reliable, scalable, and easier to manage.
