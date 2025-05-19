# Spring Boot Student Management API

This is a simple Spring Boot REST API for managing student records. The API provides endpoints to perform CRUD operations on student data.

## API Endpoints

### 1. Basic Message
- **GET** `/app/msg`
  - Returns a simple greeting message
  - Example response: `"Hello Spring Boot!"`

### 2. Get Student by Registration Number
- **GET** `/app/students/{regNo}`
  - Returns a student with the specified registration number
  - Example: `/app/students/2020ICT121`
  - Returns the student object if found, null otherwise

### 3. Get All Students
- **GET** `/app/students`
  - Returns all students as a map with registration numbers as keys
  - Example response:
    ```json
    {
      "2020ICT121": { ... },
      "2020ICT43": { ... },
      ...
    }
    ```

### 4. Add New Student
- **POST** `/app/add`
  - Accepts a student object in the request body
  - Adds the student to the collection
  - Example request body:
    ```json
    {
      "regNo": "2020ICT100",
      "name": "New Student",
      "age": 23,
      "degree": "IT",
      "gpa": 3.5
    }
    ```

### 5. Delete Student
- **DELETE** `/app/students/{id}`
  - Deletes the student with the specified registration number
  - Returns success or failure message

### 6. Update Student
- **PUT** `/app/students/{id}`
  - Updates the student with the specified registration number
  - Requires the updated student object in the request body
  - Returns success or failure message

### 7. Find Students by Age
- **GET** `/app/findage?age={age}`
  - Returns all students with the specified age
  - Example: `/app/findage?age=24`
  - Returns a list of matching students

## Screenshots

1. **Basic Message Endpoint**  
   ![GET /app/msg](screenshots/get_msg.png)

2. **Get All Students**  
   ![GET /app/students](screenshots/get_all_students.png)

3. **Get Student by Registration Number**  
   ![GET /app/students/{regNo}](screenshots/get_student_by_id.png)

4. **Add New Student**  
   ![POST /app/add](screenshots/post_add_student.png)

5. **Find Students by Age**  
   ![GET /app/findage?age=24](screenshots/get_students_by_age.png)

## How to Run

1. Ensure you have Java JDK and Maven installed
2. Clone the repository
3. Run `mvn spring-boot:run` from the project directory
4. The API will be available at `http://localhost:8080/app`

## Dependencies

- Spring Boot Web
- Lombok (for model classes)

