# Relational Schema Modeling & 3NF Normalization

## Project overview
A sample course-enrollment database built with six related tables:
Departments, Students, Instructors, Courses, Enrollments, and Payments.

## Files
- `schema.sql` — PostgreSQL DDL with primary keys, foreign keys, UNIQUE, CHECK, and NOT NULL constraints.
- `seed_data.sql` — realistic sample records for all six tables.
- `negative_tests.sql` — invalid inserts intended to be rejected by the database.
- `ER_diagram.png` — conceptual relationship diagram.

## Relationships
- Department 1:N Students
- Department 1:N Instructors
- Department 1:N Courses
- Instructor 1:N Courses
- Students N:M Courses through Enrollments
- Enrollment 1:0..1 Payment

## Normalization notes
The design separates departments, students, instructors, courses, enrollments, and payments into distinct tables. Repeating student/course details are not stored in the enrollment rows. The unique `(student_id, course_id)` constraint prevents duplicate enrollment in the same course.

## How to run
Use a PostgreSQL database. Run `schema.sql`, then `seed_data.sql`.
Run each statement in `negative_tests.sql` separately; each test insert is expected to fail.

## Important
This is a starter project. Review it, understand each table and constraint, and adapt it to your academy's exact rubric before submitting. Do not claim tests were executed unless you actually run them.
