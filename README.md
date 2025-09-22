# Overloading_in_cpp

# Polymorphism and Overloading in C++

## AIM
To explore **Polymorphism in C++** with a focus on **Overloading concepts**, including:  
- **Constructor Overloading**  
- **Function Overloading**  
- **Operator Overloading**  

---

## Introduction to Overloading in C++

In C++, **overloading** allows you to define multiple functions, constructors, or operators with the same name but different parameter lists or behaviors. Its primary purpose is to enhance:  

- **Readability**  
- **Flexibility**  
- **Reusability** of code  

The compiler determines which version to execute based on the **number or type of arguments** provided.

---

## Theory

- **Polymorphism** in C++ enables a single name to take on **multiple forms**.  
- **Overloading** is a type of **compile-time polymorphism**, where functions, constructors, or operators behave differently depending on the inputs they receive.  

---

## Constructor Overloading

**Definition:**  
Constructor overloading allows a class to have **multiple constructors with different parameter lists**.  

**Purpose:**  
Provides **flexibility in object creation**, enabling objects to be initialized in different ways depending on the arguments passed.  

**Key Points:**  
- All constructors share the **same name as the class**.  
- They are distinguished by their **parameter lists** (number or type of parameters).  
- Enhances **flexibility and readability** when creating objects.  

---

### Example: Constructor Overloading

```cpp
#include <iostream>
using namespace std;

class Student {
    string name;
    int age;

public:
    Student() { 
        name = "Unknown"; 
        age = 0; 
    }
    Student(string n) { 
        name = n; 
        age = 0; 
    }
    Student(string n, int a) { 
        name = n; 
        age = a; 
    }

    void display() { 
        cout << "Name: " << name << ", Age: " << age << endl; 
    }
};

int main() {
    Student s1;
    Student s2("Rahul");
    Student s3("Ananya", 21);

    s1.display();
    s2.display();
    s3.display();
}
```
## Function Overloading

**Definition:**  
Function overloading allows you to define **multiple functions with the same name** but with different parameter lists.

**Purpose:**  
Enables similar operations to be performed with **different types or numbers of inputs**.

**Key Points:**  
- Functions **cannot be differentiated by return type alone**.  
- Parameter lists **must differ**.  
- Improves **clarity** by reusing function names.  
- Resolution happens at **compile-time**.

### Example: Function Overloading
```cpp
#include <iostream>
using namespace std;

class Calculator {
public:
    int add(int a, int b) { return a + b; }
    int add(int a, int b, int c) { return a + b + c; }
};

int main() {
    Calculator calc;
    cout << "Sum1: " << calc.add(10, 20) << endl;
    cout << "Sum2: " << calc.add(10, 20, 30) << endl;
}
```
## Operator Overloading

**Definition:**  
Operator overloading allows you to **redefine the behavior of operators** (`+`, `-`, `*`, `==`, etc.) for **user-defined types** like classes.

**Purpose:**  
Enables objects to be used with operators in a **natural and intuitive way**, similar to primitive types.

---

### Key Points
- Achieved by defining a **function using the `operator` keyword**.  
- Improves **readability** and **usability** for custom types (e.g., complex numbers, matrices).  
- Only **existing operators** can be overloaded.  
- Some operators, such as `::`, `sizeof`, `?:`, and `.` **cannot be overloaded**.  

---

### Syntax
```cpp
class ClassName {
public:
    returnType operator op (argument) {
        // operator implementation
    }
};
```

## Differences Between Overloading Types

| Feature        | Constructor Overloading                       | Function Overloading                               | Operator Overloading                             |
|----------------|-----------------------------------------------|--------------------------------------------------|------------------------------------------------|
| **Definition** | Multiple constructors with different parameters | Multiple functions with the same name but different parameters | Redefining operators for user-defined types |
| **Purpose**    | Create objects in different ways              | Perform similar operations with different inputs | Make operators work with objects intuitively  |
| **Usage**      | Inside a class (constructors only)           | Inside or outside classes                         | With user-defined types (classes/structs)    |
| **Compile-time?** | Yes                                        | Yes                                              | Yes                                            |
| **Return Type** | Not applicable                               | Cannot overload by return type alone             | Can differ, but parameters must matter        |
| **Example Use Case** | Initialize objects in multiple ways     | Add numbers of different types                   | Add two complex numbers using `+`             |
