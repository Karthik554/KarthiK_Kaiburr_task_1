![GET_API](https://github.com/user-attachments/assets/a27fe982-d796-4dcb-8bd3-a77647cbd183)# Task 1: Java Backend and REST API  

**Author**: Aduri Karthik Chowdary  

## 📌 Overview  
This project implements a Java-based backend application that provides a REST API for managing and executing "task" objects. Each task represents a shell command that can be executed in a Kubernetes pod.  

## ✅ Features  
- Create, retrieve, search, and delete task objects via REST API  
- Store tasks along with execution details  
- Execute shell commands associated with tasks  
- Store execution results (start time, end time, and output)  

### 📝 Task  
Each task object contains:  
- **id**: Unique identifier for the task  
- **name**: Name of the task  
- **owner**: The person who created the task  
- **command**: The shell command associated with the task  
- **taskExecutions**: A list of executions for this task  

### 📊 Task Execution  
Each task execution records:  
- **startTime**: When the task started executing  
- **endTime**: When the task finished  
- **output**: The result of executing the command  

---

## 🔍 Explanation of Code Files  

### 📌 **Controller (TaskController.java)**  
- Handles incoming HTTP requests and maps them to appropriate services.  
- Provides endpoints for CRUD operations on tasks.  
- Has methods to create, retrieve, search, delete, and execute tasks.  

### 🛠️ **Service (TaskService.java)**  
- Contains the business logic of the application.  
- Handles task creation, retrieval, and execution.  
- Calls the repository to store and fetch data.  
- Executes the shell command when a task is run.  

### 🗄️ **Repository (TaskRepository.java)**  
- Interfaces with MongoDB to store task and execution details.  
- Uses Spring Data MongoDB for database interactions.  
- Provides methods to save, find, and delete tasks.  

### 📜 **Model (Task.java, TaskExecution.java)**  
- Defines the structure of `Task` and `TaskExecution` objects.  
- Annotated with Spring Boot's `@Document` to map to MongoDB collections.  

### 🚀 **Application (Main.java / TaskApplication.java)**  
- The entry point of the Spring Boot application.  
- Uses `@SpringBootApplication` annotation.  
- Runs the embedded web server.  

---

## 🔗 API Endpoints  

### 🔹 **GET /tasks**  
- Returns all tasks if no parameters are provided.  
- If a task ID is passed, returns the specific task or a `404` error if not found.
  ![GET_API](https://github.com/user-attachments/assets/1650e208-8c86-45c8-b195-3e8d61233125)


### 🔹 **POST /tasks**  
- Creates a new task.  
- Expects a JSON object with `id`, `name`, `owner`, and `command`.
  ![POST_API](https://github.com/user-attachments/assets/6156d786-114c-4c71-93b4-bb5d6011026a)


### 🔹 **GET /tasks/search?name={name}**  
- Finds tasks by name.  
- Returns all tasks that contain the given string in their name.  
 ![GET_SEARCH_API](https://github.com/user-attachments/assets/e989f8b0-cc19-4e35-84b4-cb1799fd98d5)
### MongoDB Working
![MongoDB_compass](https://github.com/user-attachments/assets/11539948-01bc-40be-a035-679910cda0f4)
### SpringBoot Application
![SPRINGBOOT_KARTHIK](https://github.com/user-attachments/assets/c9b655ca-6393-437e-b6ce-628dea1168a4)




## ⚙️ Running the Application  

### 🔹 **Requirements**  
- Java 17+  
- MongoDB  
- Postman or Curl for testing  

### 🔹 **Steps to Run**  
1. Clone the repository  
2. Start MongoDB  
3. Build and run the application using:  
   ```bash
   mvn spring-boot:run
