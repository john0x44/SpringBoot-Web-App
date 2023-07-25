# Spring Boot CRUD Web Application

This GitHub repository showcases a Spring Boot CRUD (Create, Read, Update, Delete) web application in Java.

## Project Overview

The project consists of three main packages: `com.example.demo`, `com.example.demo.model`, `com.example.demo.repository`, and `com.example.demo.service`. Each package contains specific classes that play a crucial role in the application's functionality.

### The `com.example.demo` Package

The main class of the Spring Boot application is `SpringBootCrudWebApplication.java`. This class is annotated with `@SpringBootApplication`, which tells Spring Boot to consider it as the entry point of the application. When I start the application, it launches the embedded web server and initializes the Spring context.

### The `com.example.demo.controller` Package

The `EmployeeController.java` class is the heart of the application's web layer. It handles HTTP requests and serves as the intermediary between the user interface and the business logic. The class is annotated with `@Controller`, indicating that it is a Spring MVC controller.

Here are some key methods in my `EmployeeController`:

- `viewHomePage(Model model)`: This method handles the root URL ("/") and retrieves the list of all employees from the service layer and passes it to the `index.html` template for rendering.
- `showNewEmployeeForm(Model model)`: This method handles the URL ("/showNewEmployeeForm") to display the form for creating a new employee.
- `saveEmployee(@ModelAttribute("employee") Employee employee)`: This method handles the URL ("/saveEmployee") and is responsible for saving a new employee to the database.
- `showFormForUpdate(@PathVariable(value="id") long id, Model model)`: This method handles the URL ("/showFormForUpdate/{id}") and displays the form to update an existing employee's details.
- `deleteEmployee(@PathVariable(value="id") long id)`: This method handles the URL ("/deleteEmployee/{id}") and deletes an employee from the database.

### The `com.example.demo.model` Package

The `Employee.java` class represents the model for an Employee entity. It is annotated with `@Entity`, indicating that it is a JPA entity and should be mapped to the "employees" table in the database. The class properties are mapped to columns in the database using `@Column`, and the primary key is generated using `@GeneratedValue`.

### The `com.example.demo.repository` Package

The `EmployeeRepository.java` interface extends `JpaRepository<Employee, Long>`, which provides CRUD operations for the `Employee` entity. The interface is annotated with `@Repository`, indicating that it is a Spring Data repository.

### The `com.example.demo.service` Package

The `EmployeeService.java` interface defines the contract for the service layer. It declares methods to interact with the employee data and business logic. The `EmployeeServiceImpl.java` class implements this interface and provides the actual implementation of the service methods. It is annotated with `@Service`, indicating that it is a Spring service component.

## How the Spring Boot App Works

1. When I start the application, the `SpringBootCrudWebApplication.java` class acts as the entry point and starts the embedded web server.

2. My `EmployeeController.java` handles incoming HTTP requests and delegates tasks to the `EmployeeService.java`.

3. My `EmployeeService.java` defines methods to perform CRUD operations on employees and delegates the actual database operations to the `EmployeeRepository.java`.

4. My `EmployeeRepository.java` extends `JpaRepository` to inherit common CRUD operations for the `Employee` entity from Spring Data JPA.

5. My `Employee.java` class represents the Employee entity, with its properties mapped to database columns using annotations.

6. Thymeleaf templates (`index.html`, `new_employee.html`, and `update_employee.html`) are used to render the frontend views for displaying the list of employees, creating new employees, and updating existing employees.

## Project Demo

Here are some GIFs demonstrating the application's functionality:

1. Creating an Employee:
   ![Creating an Employee](https://i.gyazo.com/1751e4a27ed6c130e93b0fcae52e6189.gif)

2. Updating an Employee:
   ![Updating an Employee](https://i.gyazo.com/c921d6d42f58cfd121074b4b786220ff.gif)

3. Deleting an Employee:
   ![Deleting an Employee](https://i.gyazo.com/a222fa8a0e6c25f9c058054cb0b0fe83.gif)

## Conclusion

This Spring Boot CRUD web application demonstrates my learning journey in building web applications using Spring Boot, Java, and Thymeleaf templates. The project includes basic CRUD operations, a well-structured MVC architecture, and the integration of a database for persistent data storage. Through this project, I have gained valuable experience in creating a Spring Boot application
