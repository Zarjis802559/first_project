# Experiment No: 04
# Submission Date: 15 October 2024

### Problem 1: Create a class called Book with attributes such as title, author, and price. Include a method to display the book's details. Write a program that instantiates a Book object and displays its details.
### Code :
```cpp
#include<iostream>
using namespace std;

class Book
{
    string title;
    string author;
    float price;

public:
    void setBookDetails(string t, string a, float p)
    {
        title = t;
        author = a;
        price = p;
    }

    void displayBookDetails()
    {
        cout << "Book Title: " << title << endl;
        cout << "Author: " << author << endl;
        cout << "Price: $" << price << endl;
    }
};

int main()
{
    Book book;
    book.setBookDetails("Paradoxical Sajid", "Arif Azad", 10.99);
    book.displayBookDetails();
    return 0;
}
```
### Output :
![image](https://github.com/user-attachments/assets/8d9448c9-fb6d-4471-bece-dde35951edfa)

### Discussion:
In this program, I created a class called Book with three attributes: title, author, and price. I implemented a method setBookDetails() to set the values for these attributes and another method displayBookDetails() to print the book's information. This code demonstrates how to create a class and use its member functions to interact with objects in C++. The program instantiates a Book object, sets its details, and then displays them.

### Problem 2: Develop a class Student that has attributes for student ID and name. Include a method to display the student's information. Create an instance of the Student class and print its details.
### Code :
```cpp
#include<iostream>
using namespace std;

class Student
{
    int studentID;
    string name;

public:
    void setStudentDetails(int id, string n)
    {
        studentID = id;
        name = n;
    }

    void displayStudentDetails()
    {
        cout << "Student ID: " << studentID << endl;
        cout << "Name: " << name << endl;
    }
};

int main()
{
    Student student;
    student.setStudentDetails(06, "Zarjis Ahammed");
    student.displayStudentDetails();
    return 0;
}
```
### Output :
![image](https://github.com/user-attachments/assets/fb2306a3-da89-4287-94b2-e6e17ecdc902)


### Discussion :
In this code, I created a Student class with two attributes: studentID and name. The method setStudentDetails() sets the values, and displayStudentDetails() prints them. This program demonstrates how to manage class attributes and display them.


### Problem 3: Implement a class called Calculator with methods for basic arithmetic operations (addition, subtraction, multiplication, division). Write a program that allows the user to perform calculations using the Calculator class.
### Code :
```cpp
#include<iostream>
using namespace std;

class Calculator
{
public:
    int add(int a, int b)
    {
        return a + b;
    }

    int subtract(int a, int b)
    {
        return a - b;
    }

    int multiply(int a, int b)
    {
        return a * b;
    }

    float divide(float a, float b)
    {
        if (b != 0)
            return a / b;
        else
            return 0; // Return 0 if division by zero
    }
};

int main()
{
    Calculator calc;
    int a = 10, b = 5;

    cout << "Addition: " << calc.add(a, b) << endl;
    cout << "Subtraction: " << calc.subtract(a, b) << endl;
    cout << "Multiplication: " << calc.multiply(a, b) << endl;
    cout << "Division: " << calc.divide(a, b) << endl;

    return 0;
}
```
### Output :
![image](https://github.com/user-attachments/assets/5eaaca2a-43ce-4f98-adb8-3ea2970b151e)


### Discussion :
This program defines a Calculator class with methods for addition, subtraction, multiplication, and division. Each method takes two operands and returns the result of the operation. The program demonstrates how the class can be used to perform basic arithmetic operations. The division method includes a check for division by zero, returning 0 if the denominator is 0.


### Problem 4: Create a Person class with attributes for name and age. Implement a method to check if the person is an adult (18 years or older). Instantiate a Person object and check if they are an adult.
### Code :
```cpp
#include<iostream>
using namespace std;

class Person
{
    string name;
    int age;

public:
    void setPersonDetails(string n, int a)
    {
        name = n;
        age = a;
    }

    bool isAdult()
    {
        return age >= 18;
    }

    void displayPersonDetails()
    {
        cout << "Name: " << name << endl;
        cout << "Age: " << age << endl;
        if (isAdult())
            cout << name << " is an adult." << endl;
        else
            cout << name << " is not an adult." << endl;
    }
};

int main()
{
    Person person;
    person.setPersonDetails("Zarjis", 21);
    person.displayPersonDetails();
    return 0;
}
```
### Output :
![image](https://github.com/user-attachments/assets/fa757209-01ce-4025-9313-34da75e5145b)


### Discussion :
In this program, the Person class contains attributes for name and age. The method isAdult() checks if the person's age is 18 or more. The program demonstrates how to use class attributes and methods to verify if a person is an adult.


### Problem 5: Design a class hierarchy with a base class Employee and subclasses Manager and Intern. Implement methods to calculate and display the salary of each type of employee. Write a program that demonstrates the use of inheritance and method overriding.
### Code :
```cpp
#include<iostream>
using namespace std;

class Employee
{
protected:
    string name;
    float baseSalary;

public:
    void setEmployeeDetails(string n, float s)
    {
        name = n;
        baseSalary = s;
    }

    virtual float calculateSalary() = 0; // Pure virtual function

    void displayEmployeeDetails()
    {
        cout << "Employee Name: " << name << endl;
        cout << "Salary: $" << calculateSalary() << endl;
    }
};

class Manager : public Employee
{
public:
    float calculateSalary()
    {
        return baseSalary + (baseSalary * 0.2); // 20% bonus
    }
};

class Intern : public Employee
{
public:
    float calculateSalary()
    {
        return baseSalary; // No bonus for interns
    }
};

int main()
{
    Manager manager;
    manager.setEmployeeDetails("Zarjis", 5000);
    manager.displayEmployeeDetails();

    Intern intern;
    intern.setEmployeeDetails("Ahnaf", 1000);
    intern.displayEmployeeDetails();

    return 0;
}
```
### Output :
![image](https://github.com/user-attachments/assets/ce2a89f3-887d-4efa-8e33-bf976537c6c3)


### Discussion :
In this program, I created a base class Employee and two derived classes: Manager and Intern. The calculateSalary() method is overridden in both subclasses to account for the different ways each type of employee is paid. The program demonstrates inheritance and method overriding in C++.


### Problem 6: Implement a class called Library that manages a collection of Book objects. Include methods to add and remove books, as well as display all available books. Write a program to test the functionality of the Library class.
### Code :
```cpp
#include<iostream>
#include<vector>
using namespace std;

class Book
{
    string title;
    string author;

public:
    Book(string t, string a) : title(t), author(a) {}

    void displayBookDetails()
    {
        cout << "Title: " << title << ", Author: " << author << endl;
    }

    string getTitle()
    {
        return title;
    }
};

class Library
{
    vector<Book> books;

public:
    void addBook(Book book)
    {
        books.push_back(book);
    }

    void removeBook(string title)
    {
        for (auto it = books.begin(); it != books.end(); ++it)
        {
            if (it->getTitle() == title)
            {
                books.erase(it);
                break;
            }
        }
    }

    void displayBooks()
    {
        cout << "Available Books:" << endl;
        for (auto& book : books)
        {
            book.displayBookDetails();
        }
    }
};

int main()
{
    Library library;
    Book book1("1984", "George Orwell");
    Book book2("To Kill a Mockingbird", "Harper Lee");

    library.addBook(book1);
    library.addBook(book2);

    library.displayBooks();

    library.removeBook("1984");
    cout << "\nAfter removing '1984':" << endl;
    library.displayBooks();

    return 0;
}
```
### Output :
![image](https://github.com/user-attachments/assets/143101a5-371b-4c9c-ad9a-831ad5d1e36d)


### Discussion :
This program demonstrates how to manage a collection of objects using the Library class. The Library class manages multiple Book objects using a vector. Methods to add, remove, and display books are implemented to test basic collection management functionality in C++.


### Problem 7: Create a class ShoppingCart that holds a list of Product objects. Implement methods to add items to the cart, remove items, and calculate the total price. Write a program to test the functionality of the ShoppingCart class.
### Code :
```cpp
#include<iostream>
#include<vector>
using namespace std;

class Product
{
    string name;
    float price;

public:
    Product(string n, float p) : name(n), price(p) {}

    string getName()
    {
        return name;
    }

    float getPrice()
    {
        return price;
    }

    void displayProduct()
    {
        cout << name << " - $" << price << endl;
    }
};

class ShoppingCart
{
    vector<Product> cart;

public:
    void addProduct(Product product)
    {
        cart.push_back(product);
    }

    void removeProduct(string name)
    {
        for (auto it = cart.begin(); it != cart.end(); ++it)
        {
            if (it->getName() == name)
            {
                cart.erase(it);
                break;
            }
        }
    }

    float calculateTotal()
    {
        float total = 0;
        for (auto& product : cart)
        {
            total += product.getPrice();
        }
        return total;
    }

    void displayCart()
    {
        cout << "Shopping Cart:" << endl;
        for (auto& product : cart)
        {
            product.displayProduct();
        }
        cout << "Total: $" << calculateTotal() << endl;
    }
};

int main()
{
    ShoppingCart cart;

    Product product1("Laptop", 999.99);
    Product product2("Headphones", 199.99);

    cart.addProduct(product1);
    cart.addProduct(product2);

    cart.displayCart();

    cart.removeProduct("Laptop");
    cout << "\nAfter removing 'Laptop':" << endl;
    cart.displayCart();

    return 0;
}
```
### Output :
![image](https://github.com/user-attachments/assets/bb80e22d-8f6f-461d-bcc8-3ba9251e5494)

### Discussion :
In this program, I designed a ShoppingCart class that manages a list of Product objects. The program allows the user to add and remove products from the cart and calculates the total price. This demonstrates object composition and basic collection management in C++.

### Problem 8: Write an abstract class called Appliance with an abstract method turnOn(). Create subclasses WashingMachine and Refrigerator that implement this method. Write a program that demonstrates method overriding (function overriding).
### Code :
```cpp
#include<iostream>
using namespace std;

class Appliance
{
public:
    virtual void turnOn() = 0; // Pure virtual function
};

class WashingMachine : public Appliance
{
public:
    void turnOn()
    {
        cout << "Washing Machine is now ON." << endl;
    }
};

class Refrigerator : public Appliance
{
public:
    void turnOn()
    {
        cout << "Refrigerator is now ON." << endl;
    }
};

int main()
{
    WashingMachine wm;
    Refrigerator fridge;

    wm.turnOn();
    fridge.turnOn();

    return 0;
}
```
### Output :
![image](https://github.com/user-attachments/assets/c0771e38-b2e8-4f90-b499-2dfaee55ce89)


### Discussion :
In this program, I created an abstract class Appliance with a pure virtual function turnOn(). Two subclasses, WashingMachine and Refrigerator, implement this method. The program demonstrates method overriding in C++.


### Problem 9: Design a class School that manages a collection of Student objects. Implement methods to add, remove, and search for students by ID. Write a program to test the School class.
### Code :
```cpp
#include<iostream>
#include<vector>
using namespace std;

class Student
{
    string name;
    int id;

public:
    Student(string n, int i) : name(n), id(i) {}

    int getId() { return id; }
    void displayInfo()
    {
        cout << "ID: " << id << ", Name: " << name << endl;
    }
};

class School
{
    vector<Student> students;

public:
    void addStudent(Student student)
    {
        students.push_back(student);
    }

    void removeStudent(int id)
    {
        for (auto it = students.begin(); it != students.end(); ++it)
        {
            if (it->getId() == id)
            {
                students.erase(it);
                break;
            }
        }
    }

    void searchStudent(int id)
    {
        for (auto& student : students)
        {
            if (student.getId() == id)
            {
                student.displayInfo();
                return;
            }
        }
        cout << "Student not found." << endl;
    }

    void displayAllStudents()
    {
        cout << "All Students:" << endl;
        for (auto& student : students)
        {
            student.displayInfo();
        }
    }
};

int main()
{
    School school;
    school.addStudent(Student("Zarjis", 06));
    school.addStudent(Student("Adib", 11));

    school.displayAllStudents();

    cout << "\nSearching for student with ID 101:" << endl;
    school.searchStudent(101);

    school.removeStudent(101);
    cout << "\nAfter removing student with ID 101:" << endl;
    school.displayAllStudents();

    return 0;
}
```
### Output :
![image](https://github.com/user-attachments/assets/e4ed217a-c3b8-4a6f-9b82-00ce5fd33411)


### Discussion :
This program demonstrates how to manage a collection of Student objects using the School class. It allows adding, removing, and searching for students by ID, showcasing basic collection management in C++.


### Problem 10: Create a class Game that has methods to start, pause, and end the game. Implement a method to display the game's status. Write a program that simulates a simple game using the Game class.
### Code :
```cpp
#include<iostream>
using namespace std;

class Game
{
private:
    string status;

public:
    Game() : status("Stopped") {}

    void start()
    {
        status = "Running";
        cout << "Game started." << endl;
    }

    void pause()
    {
        status = "Paused";
        cout << "Game paused." << endl;
    }

    void end()
    {
        status = "Stopped";
        cout << "Game ended." << endl;
    }

    void displayStatus()
    {
        cout << "Current Game Status: " << status << endl;
    }
};

int main()
{
    Game myGame;

    myGame.displayStatus();
    myGame.start();
    myGame.displayStatus();
    myGame.pause();
    myGame.displayStatus();
    myGame.end();
    myGame.displayStatus();

    return 0;
}
```
### Output :
![image](https://github.com/user-attachments/assets/b33dcf87-2048-42da-a511-6b2bd694313c)


### Discussion :
In this program, I created a Game class that simulates the status of a game. The methods start(), pause(), and end() modify the game status, and the displayStatus() method shows the current state. This demonstrates basic class functionality in C++.


### Problem 11: Design a class Person that includes a static variable to count the number of Person objects created. Implement a method to display the total count of persons. Write a program that creates several Person objects and displays the count.
### Code :
```cpp
#include<iostream>
using namespace std;

class Person
{
private:
    static int count; // Static variable to keep track of the number of Person objects
    string name;

public:
    Person(string n) : name(n)
    {
        count++;
    }

    ~Person()
    {
        count--;
    }

    static void displayCount()
    {
        cout << "Total Persons Created: " << count << endl;
    }
};

int Person::count = 0; // Initialize static variable

int main()
{
    Person p1("Ahnaf");
    Person p2("Nadeem");
    Person p3("Zarjis");

    Person::displayCount(); // Display count of Person objects

    {
        Person p4("Adib");
        Person::displayCount(); // Display count after creating one more object
    }

    Person::displayCount(); // Display count after p4 goes out of scope

    return 0;
}
```
### Output :
![image](https://github.com/user-attachments/assets/ac9531ef-3621-4f2f-b72e-8e503d227553)


### Discussion :
This program demonstrates how to use static variables in a class. The Person class keeps track of how many objects have been created using a static variable. The program showcases object creation, destruction, and maintaining a count of active objects.


### Problem 12: Define a class Complex with private members real and imaginary. Overload the operators +, -, *, and / to perform addition, subtraction, multiplication, and division of two complex numbers, respectively. Create a constructor to initialize the complex number and include a method to display the result. The main() function should be used to test these overloaded operators.
### Code :
```cpp
#include<iostream>
using namespace std;

class Complex
{
private:
    float real;
    float imaginary;

public:
    Complex(float r, float i) : real(r), imaginary(i) {}

    Complex operator+(const Complex& c)
    {
        return Complex(real + c.real, imaginary + c.imaginary);
    }

    Complex operator-(const Complex& c)
    {
        return Complex(real - c.real, imaginary - c.imaginary);
    }

    Complex operator*(const Complex& c)
    {
        return Complex(real * c.real - imaginary * c.imaginary,
                       real * c.imaginary + imaginary * c.real);
    }

    Complex operator/(const Complex& c)
    {
        float denominator = c.real * c.real + c.imaginary * c.imaginary;
        return Complex((real * c.real + imaginary * c.imaginary) / denominator,
                       (imaginary * c.real - real * c.imaginary) / denominator);
    }

    void display()
    {
        cout << real << " + " << imaginary << "i" << endl;
    }
};

int main()
{
    Complex c1(3, 2);
    Complex c2(1, 7);

    Complex sum = c1 + c2;
    Complex diff = c1 - c2;
    Complex prod = c1 * c2;
    Complex quot = c1 / c2;

    cout << "c1: ";
    c1.display();
    cout << "c2: ";
    c2.display();
    cout << "Sum: ";
    sum.display();
    cout << "Difference: ";
    diff.display();
    cout << "Product: ";
    prod.display();
    cout << "Quotient: ";
    quot.display();

    return 0;
}
```
### Output :
![image](https://github.com/user-attachments/assets/22747e34-3e33-46d1-97e6-a1aaad2865ac)


### Discussion :
This program demonstrates operator overloading in the Complex class for addition, subtraction, multiplication, and division of complex numbers. Each overloaded operator returns a new Complex object, allowing for intuitive arithmetic with complex numbers.

### Problem 13: Define a class Rectangle with private members length and breadth. Overload the operators == to check if two rectangles have equal areas, and > and < to compare if one rectangle is larger or smaller than the other based on area. Implement a constructor to initialize the rectangle's dimensions and a method to calculate its area. The main() function should test the overloaded operators.
### Code :
```cpp
#include<iostream>
using namespace std;

class Rectangle
{
private:
    float length;
    float breadth;

public:
    // Constructor to initialize length and breadth
    Rectangle(float l, float b) : length(l), breadth(b) {}

    // Method to calculate the area of the rectangle
    float area() const
    {
        return length * breadth;
    }

    // Overload == operator to compare if two rectangles have equal areas
    bool operator==(const Rectangle& r)
    {
        return this->area() == r.area();
    }

    // Overload > operator to check if one rectangle's area is larger than the other
    bool operator>(const Rectangle& r)
    {
        return this->area() > r.area();
    }

    // Overload < operator to check if one rectangle's area is smaller than the other
    bool operator<(const Rectangle& r)
    {
        return this->area() < r.area();
    }

    // Method to display the area of the rectangle
    void displayArea()
    {
        cout << "Area: " << area() << endl;
    }
};

int main()
{
    // Create three Rectangle objects
    Rectangle rect1(4, 5);
    Rectangle rect2(2, 10);
    Rectangle rect3(3, 6);

    // Display the areas of the rectangles
    rect1.displayArea();
    rect2.displayArea();
    rect3.displayArea();

    // Compare rect1 and rect2 using the overloaded == operator
    if (rect1 == rect2)
        cout << "rect1 and rect2 have equal areas." << endl;
    else
        cout << "rect1 and rect2 do not have equal areas." << endl;

    // Compare rect1 and rect3 using the overloaded > and < operators
    if (rect1 > rect3)
        cout << "rect1 is larger than rect3." << endl;
    else if (rect1 < rect3)
        cout << "rect1 is smaller than rect3." << endl;

    return 0;
}
```
### Output :
![image](https://github.com/user-attachments/assets/aa66cf16-bf97-4c2c-8971-d715fbf8d0eb)


### Discussion :
This program demonstrates operator overloading for comparing the areas of two rectangles using the ==, >, and < operators. The program creates three Rectangle objects, calculates their areas, and compares them based on their area. This approach simplifies the process of comparing rectangles using custom logic in C++.
