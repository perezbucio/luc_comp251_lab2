# Lab 2 - Conceptual Modeling using Draw.io

## Entities

### STUDENT
A person enrolled at the school who attends courses.
- Possible attributes: `student_id` (identifier), `student_name`, `student_address`

### SEAT
A physical seat that a student occupies.
- Possible attributes: `seat_no` (identifier), `seat_position`

### INSTRUCTOR
A staff member who teaches courses.
- Possible attributes: `instructor_no` (identifier), `instructor_name`, `instructor_faculty`

### COURSE
A subject offered by the school.
- Possible attributes: `course_number` (identifier), `course_name`

### SECTION
A specific offering of a course.
- Possible attributes: `section_number` (identifier)

### PROFESSOR
A faculty member who teaches sections.
- Possible attributes: `professor_id` (identifier), `professor_name`, `professor_faculty`

### ENROLLMENT (associative entity)
Resolves the many-to-many relationship between STUDENT and COURSE. Each record is one student taking one course.
- Possible attributes: `student_id`, `course_number`

### COURSE_SECTION (associative entity)
Resolves the many-to-many relationship between COURSE and SECTION. Each record links one course to one section.
- Possible attributes: `course_number`, `section_number`

## Relationships

### From the original diagram
- Each **STUDENT** <u>fills</u> one and only one **SEAT**.
- Each **SEAT** <u>is filled by</u> one and only one **STUDENT**.

- Each **STUDENT** <u>takes</u> one or many **COURSES**.
- Each **COURSE** <u>is taken by</u> one or many **STUDENTS**.

- Each **INSTRUCTOR** <u>teaches</u> one or many **COURSES**.
- Each **COURSE** <u>is taught by</u> one and only one **INSTRUCTOR**.

- Each **COURSE** <u>has</u> one or many **SECTIONS**.
- Each **SECTION** <u>belongs to</u> one or many **COURSES**.

- Each **PROFESSOR** <u>teaches</u> zero or many **SECTIONS**.
- Each **SECTION** <u>is taught by</u> one and only one **PROFESSOR**.

### From the associative entities
- Each **STUDENT** <u>has</u> zero or many **ENROLLMENTS**.
- Each **ENROLLMENT** <u>belongs to</u> one and only one **STUDENT**.
- Each **COURSE** <u>has</u> zero or many **ENROLLMENTS**.
- Each **ENROLLMENT** <u>belongs to</u> one and only one **COURSE**.

- Each **COURSE** <u>is listed in</u> zero or many **COURSE_SECTIONS**.
- Each **COURSE_SECTION** <u>belongs to</u> one and only one **COURSE**.
- Each **SECTION** <u>is listed in</u> zero or many **COURSE_SECTIONS**.
- Each **COURSE_SECTION** <u>belongs to</u> one and only one **SECTION**.

## Assumptions

Based on what the school ERD shows:

| Assumption | Answer |
|---|---|
| Does every student fill a seat? | Yes |
| Can a student fill more than one seat? | No |
| Can a seat be filled by more than one student? | No |
| Can a student take more than one course? | Yes |
| Can a course be taken by more than one student? | Yes |
| Must a student take at least one course? | Yes |
| Can an instructor teach more than one course? | Yes |
| Must an instructor teach at least one course? | Yes |
| Can a course be taught by more than one instructor? | No |
| Can a course have more than one section? | Yes |
| Can a section belong to more than one course? | Yes |
| Can a section be taught by more than one professor? | No |
| Can a professor teach more than one section? | Yes |
| Can a professor exist without teaching a section? | Yes |
| Can an enrollment exist without a student or a course? | No |
| Can a course exist without any enrollments yet? | Yes |

## ER Diagram
###
- <img width="832" height="624" alt="image" src="https://github.com/user-attachments/assets/08ca0f35-cdf8-4a66-ab52-8105a3380cdc" />
