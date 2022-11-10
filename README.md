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
  - Each of the methods above should return a `Double`.
  - Each of these methods will use the `@GetMapping` annotation with the method
    name as the path (i.e., "/add" will be the route for the `add()` method).
    - Since each of these methods will take in two parameters, the full URL
      might look like: `http://localhost:8080/add?x=8&y=4` where x and y are
      the request parameters.
- Create a `CalculatorService` class. This will be where we place the business
  logic.
  - The service will need to have the following methods:
    - sum
    - difference
    - product
    - quotient
  - Each of the methods above should take in two numbers as parameters and return
    a `Double`.
  - For the `subtract()` and `divide()` methods, the first number argument will
    be the minuend or the dividend respectfully.
    - If the first parameter in a subtraction method is 5, then 5 will be the
      number we subtract from.
    - If the first parameter in a division method is 5, then 5 will be the number
      that is being divided.
  - Remember, anything divided by 0 is not a number. Print an error to the console
    and return null when 0 is given as divisor (second number).
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

Consider the example outputs:

### Addition

Request URL: `http://localhost:8080/add?x=8&y=4`

![Postman-add-request](https://curriculum-content.s3.amazonaws.com/spring-mod-1/mvc-lab/mvc-lab-add.png)

### Subtraction

Request URL: `http://localhost:8080/subtract?x=8&y=4`

![Postman-subtract-request](https://curriculum-content.s3.amazonaws.com/spring-mod-1/mvc-lab/mvc-lab-subtract.png)

### Multiplication

Request URL: `http://localhost:8080/multiply?x=8&y=4`

![Postman-multiply-request](https://curriculum-content.s3.amazonaws.com/spring-mod-1/mvc-lab/mvc-lab-multiply.png)

### Division

Request URL: `http://localhost:8080/divide?x=8&y=4`

![Postman-divide-request](https://curriculum-content.s3.amazonaws.com/spring-mod-1/mvc-lab/mvc-lab-divide.png)

Request URL: `http://localhost:8080/divide?x=8&y=0`

Note that request above will attempt to divide by 0; which should return null
since anything divided by 0 is not a number.

![Postman-divide-by-zero](https://curriculum-content.s3.amazonaws.com/spring-mod-1/mvc-lab/mvc-lab-divide-zero-postman.png)

![Console-error-divide-by-0](https://curriculum-content.s3.amazonaws.com/spring-mod-1/mvc-lab/mvc-lab-divide-zero-console-error.png)