# University Database Management System

This project represents a **relational database schema** designed to manage data for a university environment. It includes entities for students, courses, academic programs, and their relationships.

## 📌 Project Overview

The system is built using **Microsoft SQL Server Management Studio** and follows a normalized database structure to ensure data integrity and efficiency. It is designed to:

- Track students and their enrollment in programs.
- Assign courses to academic programs by semester and year.
- Record course enrollment and performance of students.

## 🧩 Entity Descriptions

### 🔹 Program
Represents an academic program (e.g., Computer Science).
- `programId`: Primary key.
- `programName`: Name of the program.
- `commencementYear`: Year the program started.
- `totalCreditPoints`: Total credits required to complete the program.

### 🔹 Course
Represents a university course.
- `courseId`: Primary key.
- `courseName`: Course title.
- `creditPoints`: Number of credit points.
- `commencementYear`: Year the course started.

### 🔹 Student
Stores student information.
- `studentId`: Primary key.
- `programId`: Foreign key to `Program`.
- `firstName`: First name of the student.
- `lastName`: Last name of the student.
- `birthDate`: Date of birth.

### 🔹 programCourse
Represents the relationship between programs and the courses they offer.
- Composite primary key: `programId`, `courseId`.
- `year`: Academic year of the course.
- `semester`: Semester number.

### 🔹 studentCourse
Represents the enrollment of students in courses.
- Composite primary key: `studentId`, `courseId`.
- `mark`: Numerical score achieved.
- `grade`: Letter grade.
- `enrollmentYear`: Year of enrollment in the course.
- `semester`: Semester in which the course was taken.

## 🧪 How to Use

1. Open the project in SQL Server Management Studio.
2. Review or modify the schema diagram under the **University** database.
3. Insert records into the tables using `INSERT` statements.
4. Run queries to generate reports, such as student grades, course enrollment statistics, or program summaries.

## 📂 Project Structure

- `dbo.Program`: Table for programs.
- `dbo.Course`: Table for courses.
- `dbo.Student`: Table for students.
- `dbo.programCourse`: Bridge table between programs and courses.
- `dbo.studentCourse`: Bridge table between students and courses.

## ✅ Features

- Referential integrity using foreign keys.
- Support for many-to-many relationships (e.g., students ↔ courses, programs ↔ courses).
- Logical separation of concerns using proper normalization.
- Easily extendable for future modules such as attendance, instructors, or departments.

## 📸 ER Diagram

The full ER diagram is available in the `UniversityDiagram.png` image.

---

Created  using SQL Server and ER modeling best practices.
