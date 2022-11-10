# Spring Web MVC Lab

## Learning Goals

- Practice creating a web application using the Spring Framework.
- Create a `@Controller` class.
- Create a `@Service` class.
- Use Postman as an API Client tool to test.

## Instructions

Create a simple web application using the Spring Framework to perform simple
calculator operations between two numbers.

Follow the given instructions and tips:

- Create a `CalculatorController` class. This will be the controller class.
  - The controller will need to have the following methods:
    - add
    - subtract
    - multiply
    - divide
  - Each of the methods above should take in two numbers as request parameters.
  - Each of the methods above should return a `double`.
  - Each of these methods will use the `@GetMapping` annotation with the method
    name as the path (i.e., "/add" will be the route for the `add()` method).
- Create a `CalculatorService` class. This will be where we place the business
  logic.
  - The service will need to have the following methods:
    - sum
    - difference
    - product
    - quotient
  - Each of the methods above should take in two numbers as parameters and return
    a `double`.
  - For the `subtract()` and `divide()` methods, the first number argument will
    be the minuend or the dividend respectfully.
    - If the first parameter in a subtraction method is 5, then 5 will be the
      number we subtract from.
    - If the first parameter in a division method is 5, then 5 will be the number
      that is being divided.
  - Add the service to the controller class as we saw in the Service Class
    lesson.
    - Add a `private final` reference to the `CalculatorService` class to the
      controller class.
    - Add an `@Autowired` constructor to the controller class.
- Use the `SpringMod1MvcLabApplication` class to run the application.
- Use Postman to test the application.

## Project Structure

The Spring Boot project has already been initialized for you. Consider the
following project structure:

```text
├── CONTRIBUTING.md
├── HELP.md
├── LICENSE.md
├── mvnw
├── mvnw.cmd
├── pom.xml
├── README.md
└── src
    ├── main
    │   ├── java
    │   │   └── com
    │   │       └── example
    │   │           └── springmod1mvclab
    │   │               ├── SpringMod1MvcLabApplication.java
    │   │               ├── controller
    │   │               │   └── CalculatorController.java
    │   │               └── service
    │   │                   └── CalculatorService.java
    │   └── resources
    │       ├── application.properties
    │       ├── static
    │       └── templates
    └── test
        └── java
            └── org
                └── example
                    └── springmod1mvclab
                        └── SpringMod1MvcLabApplication.java
```

## Example Output

123456789101112131415161718192021222324252627ac28293031323334353637383940404143454