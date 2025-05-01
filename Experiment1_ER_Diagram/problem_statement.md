# Experiment 1: Entity-Relationship (ER) Diagram

## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

## 🧪 Choose One Scenario:

### 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

**User Requirements:**
- Academic programs grouped under departments.
- Students have admission number, name, DOB, contact info.
- Instructors with staff number, contact info, etc.
- Courses have number, name, credits.
- Track course enrollments by students and enrollment date.
- Add support for prerequisites (some courses require others).

---

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# ER Diagram Submission - Mohammed Ali.S

## Scenario Chosen:
University / Hospital (choose one)

## ER Diagram:
University:

![image](https://github.com/user-attachments/assets/eff1d94b-db29-4c2f-bca1-125d5a7d2f0b)

## Entities and Attributes:
Student

AdmissionNumber (PK)

Name

DateOfBirth

ContactInfo

Instructor

StaffNumber (PK)

Name

ContactInfo

Department

Program

ProgramID (PK)

ProgramName

Department

Course

CourseNumber (PK)

CourseName

Credits

Enrollment

AdmissionNumber (FK)

CourseNumber (FK)

EnrollmentDate

Department

DepartmentID (PK)

DepartmentName

Prerequisite

CourseNumber (FK)

PrerequisiteCourseNumber (FK)
...

## Relationships and Constraints:
Student - Enrolls - Course

Many-to-Many (since a student can enroll in many courses, and a course can have many students)

Participation: Total for Student (must enroll in at least one course)

Instructor - Teaches - Course

One-to-Many (one instructor can teach many courses; each course taught by one instructor)

Participation: Partial for Instructor

Program - Offers - Course

One-to-Many (each program offers multiple courses)

Student - EnrolledIn - Program

Many-to-One (each student belongs to one program)

Department - Has - Program / Instructor

One-to-Many (department has multiple programs and instructors)

Course - Has - Prerequisite

Recursive Relationship

One-to-Many (a course can have multiple prerequisites)



## Extension (Prerequisite / Billing):
The Prerequisite relationship is a recursive relationship on the Course entity. Each course can be related to another course that is a prerequisite for it. This is modeled using:

CourseNumber → the course that requires prerequisites

PrerequisiteCourseNumber → the course that must be completed before

This helps in course planning and validation during student registration.

## Design Choices:
Separate Prerequisite entity: For flexibility and to handle multiple prerequisites per course.

Associative Entity for Enrollment: To track when students enroll and to support many-to-many relationships.

Department as central: Because both programs and instructors are grouped under departments.

Recursive relationship: To handle course prerequisites elegantly without duplication.
## RESULT
Successfully created an ER diagram that represents a university system with clear entities, relationships, and constraints, including the prerequisite mechanism for courses.

