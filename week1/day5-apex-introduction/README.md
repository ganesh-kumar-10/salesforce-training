# Day 5 – Apex Introduction

# What is Apex?

Apex is Salesforce’s object-oriented programming language used to implement custom business logic on the Lightning Platform.

It is similar to Java and is tightly integrated with Salesforce CRM and database objects.

Apex allows developers to:
- Automate business processes
- Create triggers
- Build custom validations
- Integrate external systems
- Perform complex calculations
- Execute asynchronous operations

---

# Flow vs Apex

| Feature | Flow | Apex |
|---|---|---|
| Type | No-code/Low-code | Full programming |
| Complexity Handling | Medium | Very High |
| UI Based | Yes | No |
| Reusability | Limited | High |
| Debugging | Simple | Advanced |
| External Integrations | Limited | Powerful |
| Performance Control | Less | More |
| Best For | Standard automation | Complex enterprise logic |

## Example

### Flow Example
- Send email after student registration

### Apex Example
- Calculate scholarship eligibility using multiple academic rules

---

# Configuration vs Coding

| Configuration | Coding |
|---|---|
| Click-based setup | Written program logic |
| Faster for simple tasks | Better for complex requirements |
| Easy for admins | Requires developers |
| Limited flexibility | Highly customizable |
| Declarative | Programmatic |

---

# Real Examples Where Apex Is Needed

## 1. Complex Fee Calculation

### Problem
Student fees depend on:
- Scholarship percentage
- Attendance
- Course type
- Hostel facility
- Late payment penalties

### Why Flow Is Not Enough
The logic becomes too large and difficult to maintain visually.

### Why Apex Is Needed
Apex handles:
- Multiple conditions
- Nested calculations
- Reusable logic
- Better performance

---

## 2. Integration with External Payment System

### Problem
The college system must connect with:
- Razorpay
- Stripe
- Banking APIs

### Why Flow Is Not Enough
External API handling requires:
- Authentication
- JSON parsing
- Error handling

### Why Apex Is Needed
Apex supports:
- REST callouts
- SOAP APIs
- Secure integrations
- Async processing

---

## 3. Advanced Eligibility Logic

### Problem
Student eligibility depends on:
- Attendance percentage
- Previous semester GPA
- Discipline records
- Pending fee payments

### Why Flow Is Not Enough
Complex multi-object conditions become difficult to manage.

### Why Apex Is Needed
Apex provides:
- Efficient queries
- Custom algorithms
- Better maintainability

---

# Integrated College Management System Design

# CRM Usage

Salesforce CRM is used to manage:
- Student admissions
- Courses
- Faculty assignments
- Notifications
- Academic records

---

# Objects Used

| Object | Purpose |
|---|---|
| Student__c | Store student details |
| Course__c | Store course information |
| Faculty__c | Store faculty data |
| Enrollment__c | Manage course registrations |

---

# Relationships

## Student ↔ Course
- Many-to-Many relationship
- Managed using Enrollment__c junction object

## Faculty ↔ Course
- One faculty teaches many courses

---

# Validation Rules

## Example
Prevent saving student record if email is empty.

### Rule
```text
ISBLANK(Email__c)
```

### Error Message
```text
Email is required.
```

---

# Formula Field

## Remaining Seats Formula

```text
Total_Seats__c - Enrolled_Students__c
```

This dynamically shows available seats in a course.

---

# Flow Automation

## Auto Notification Flow

### Process
1. Student registers
2. Flow triggers automatically
3. Confirmation email sent
4. Enrollment status updated

---

# Apex Business Logic

## Example Rule

Block registration if:
- Remaining seats = 0
- Student attendance < 75%
- Fees pending

### Why Apex?
This logic involves:
- Multiple objects
- Complex conditions
- Custom validations

---

# Apex Thinking Exercise

## Cases Where Flow Is NOT Enough

| Scenario | Why Apex Is Needed |
|----------|-------------------|
| Complex Fee Calculation | Multiple nested calculations |
| External Payment Integration | API callouts and JSON handling |
| Advanced Eligibility Logic | Multi-object custom logic |

---

# Pseudocode Examples

## Example 1 – Seat Availability
```text
IF remaining seats <= 0
THEN block registration
ELSE allow registration
```

## Example 2 – Attendance Warning
```text
IF attendance < 75%
THEN send notification to student
```

## Example 3 – Fee Pending
```text
IF fee_status = pending
THEN prevent exam hall ticket generation
```

---

# Reflection

## Why can’t all enterprise logic be built using only clicks and configuration?

Enterprise systems often involve:
- Complex calculations
- Large-scale data processing
- External integrations
- Advanced validations
- Dynamic business rules

No-code tools like Flow are powerful for standard automation, but they become difficult to maintain when business requirements become highly complex.

Programming languages like Apex provide:
- Flexibility
- Scalability
- Reusability
- Better performance
- Fine-grained control

Therefore, enterprise applications eventually require coding to handle real-world complexity efficiently.
