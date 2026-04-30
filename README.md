
***Exp-7 spring boot rest api
Main Application-HarshDemoApplication.java(class).
package com.example.demo;
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
@SpringBootApplication
public class HarshDemoApplication
{
public static void main(String[] args)
{
SpringApplication.run(HarshDemoApplication.class, args);
}
}



REST Controller
Create file:
HarshController.java
package com.example.demo;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;
@RestController
public class HarshController
{
@GetMapping("/welcomeharsh")
public String welcomeHarsh()
{
return "Hey Harsh, This is your first Springboot Application running";
}
}


*******Exp-1 class and object
class Rectangle {
int length;
int width;
int area;
}
public class Shape {
public static void main(String args[]) {
Rectangle rect = new Rectangle();
rect.length = 20;
rect.width = 30;
rect.area = rect.length * rect.width;
System.out.println("Length: " + rect.length);
System.out.println("Width: " + rect.width);
System.out.println("Area: " + rect.area);
}
}


constructor
class Student {
int rollNo;
String name;
// Default Constructor
Student() {
rollNo = 0;
name = "Not Assigned";
}
// Parameterized Constructor
Student(int r, String n) {
rollNo = r;
name = n;
}
void display() {
System.out.println("Roll No: " + rollNo);
System.out.println("Name: " + name);
}
}
public class ConstructorDemo {
public static void main(String[] args) {
Student s1 = new Student();
Student s2 = new Student(22, "Harsh");
s1.display();
s2.display();
}
}



***Exp-8 postman
Controller Class
package com.example.demo;
import org.springframework.web.bind.annotation.;
import java.util.;
@RestController
@RequestMapping("/api")
public class StudentController {
List students = new ArrayList<>();
// GET API
@GetMapping("/students")
public List getStudents() {
return students;
}
// POST API
@PostMapping("/students")
public String addStudent(@RequestBody String name) {
students.add(name);
return "Student added successfully";
}
// PUT API
@PutMapping("/students/{index}")
public String updateStudent(@PathVariable int index, @RequestBody String name) {
students.set(index, name);
return "Student updated successfully";
}
// DELETE API
@DeleteMapping("/students/{index}")
public String deleteStudent(@PathVariable int index) {
students.remove(index);
return "Student deleted successfully";
}
}
postman if required
--1. GET Request
Method: GET
URL: http://localhost:8080/api/students⁠�
Response: ["Harsh"]
POST Request
Method: POST
URL: http://localhost:8080/api/students⁠�
Body (Raw JSON):
"Harsh"
Response:
Student added successfully
PUT Request
Method: PUT
URL: http://localhost:8080/api/students/0⁠�
Body:
"Harsh"
Response:
Student updated successfully
DELETE Request
Method: DELETE
URL: http://localhost:8080/api/students/0⁠�
Response:
Student deleted successfully
