# TaskManager Project

## **Overview**
TaskManager is a Spring Boot application designed to demonstrate fundamental backend development concepts. The application offers three primary features:
- **Task Management**: Add, delete, and retrieve tasks stored in memory.
- **Mathematical Operations**: Perform basic arithmetic calculations.
- **String Manipulations**: Reverse strings, count vowels, and change text case.

This project is built with simplicity in mind, making it a perfect starting point for understanding Spring Boot development.

---

## **Features**

### **1. Task Management**
Manage tasks in memory using a simple interface:
- **Add tasks**
- **Retrieve all tasks**
- **Delete tasks by ID**

### **2. Mathematical Operations**
Perform basic arithmetic:
- **Addition**: `/math/add?a=5&b=10`
- **Subtraction**: `/math/subtract?a=10&b=5`
- **Multiplication**: `/math/multiply?a=5&b=4`
- **Division**: `/math/divide?a=10&b=2`

### **3. String Manipulations**
Process strings with endpoints for:
- **Reversing strings**: `/strings/reverse?input=hello`
- **Counting vowels**: `/strings/count-vowels?input=education`
- **Converting text to uppercase**: `/strings/to-upper?input=hello world`

---

## **Project Structure**

```
src
├── main
│   ├── java
│   │   └── com.example.taskmanager
│   │       ├── controller    # REST controllers for handling HTTP requests
│   │       ├── service       # Business logic for tasks, math, and strings
│   │       ├── model         # Task model definition
│   │       └── exception     # Custom exception handling
│   ├── resources
│       └── application.properties  # Configuration file
└── test
    └── java
        └── com.example.taskmanager # Unit tests (optional)
```

---

## **Endpoints**

### **Task Management**
| Method | Endpoint       | Description             | Example Request Body                              |
|--------|----------------|-------------------------|--------------------------------------------------|
| GET    | `/tasks`       | Get all tasks          | N/A                                              |
| POST   | `/tasks`       | Add a new task         | `{"id": 1, "name": "Sample Task", "completed": false}` |
| DELETE | `/tasks/{id}`  | Delete a task by ID    | N/A                                              |

---

### **Math Operations**
| Method | Endpoint        | Description           | Example Query Parameters |
|--------|-----------------|-----------------------|--------------------------|
| GET    | `/math/add`     | Add two numbers       | `?a=5&b=10`              |
| GET    | `/math/subtract`| Subtract two numbers  | `?a=10&b=5`              |
| GET    | `/math/multiply`| Multiply two numbers  | `?a=5&b=4`               |
| GET    | `/math/divide`  | Divide two numbers    | `?a=10&b=2`              |

---

### **String Manipulations**
| Method | Endpoint           | Description                 | Example Query Parameters |
|--------|--------------------|-----------------------------|--------------------------|
| GET    | `/strings/reverse` | Reverse the input string    | `?input=hello`           |
| GET    | `/strings/count-vowels` | Count vowels in input string | `?input=education`       |
| GET    | `/strings/to-upper`| Convert input string to uppercase | `?input=hello world` |

---

## **Error Handling**

- **Arithmetic Errors**: Returns a `400 BAD REQUEST` (e.g., division by zero).
- **Generic Errors**: Returns a `500 INTERNAL SERVER ERROR` with a descriptive message.

---

## **How to Run**

### **Prerequisites**
1. Java 17 or higher.
2. Maven or Gradle.
3. Postman or any REST client for testing.

### **Steps**
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/taskmanager.git
   cd taskmanager
   ```
2. Build the project:
   ```bash
   ./gradlew build
   ```
3. Run the application:
   ```bash
   ./gradlew bootRun
   ```
4. Access the API at `http://localhost:8080`.

---

## **Sample Requests**

### **Task Management**
- Add a task:
  ```bash
  curl -X POST -H "Content-Type: application/json" \
  -d '{"id": 1, "name": "Sample Task", "completed": false}' \
  http://localhost:8080/tasks
  ```

- Get all tasks:
  ```bash
  curl http://localhost:8080/tasks
  ```

- Delete a task:
  ```bash
  curl -X DELETE http://localhost:8080/tasks/1
  ```

### **Math Operations**
- Add two numbers:
  ```bash
  curl http://localhost:8080/math/add?a=5&b=10
  ```

- Divide two numbers:
  ```bash
  curl http://localhost:8080/math/divide?a=10&b=0
  ```

### **String Manipulations**
- Reverse a string:
  ```bash
  curl http://localhost:8080/strings/reverse?input=hello
  ```

---

## **Technologies Used**
- **Java**: Programming language.
- **Spring Boot**: Backend framework.
- **Gradle**: Build tool.
- **Postman**: API testing.

---

## **Future Enhancements**
- Persist tasks in a database.
- Add authentication for sensitive endpoints.
- Expand mathematical and string manipulation functionalities.

---

Feel free to clone, test, and improve the project! 🚀 
