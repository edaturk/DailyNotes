Dynamic polymorphism is a programming concept in object-oriented languages like C++ where a derived class can override or redefine methods of its base class. This means that a single method call can have different implementations based on the type of object it is called on.

Dynamic polymorphism is achieved through **virtual functions**, which are member functions of a base class marked with the `virtual` keyword.
```
#include <iostream>

// Base class
class Shape {
public:
    virtual void draw() {
        std::cout << "Drawing a shape" << std::endl; 
    }
};

// Derived class 1
class Circle : public Shape {
public:
    void draw() override {
        std::cout << "Drawing a circle" << std::endl; 
    }
};

// Derived class 2
class Rectangle : public Shape {
public:
    void draw() override {
        std::cout << "Drawing a rectangle" << std::endl;
    }
};

int main() {
    Shape* shape;
    Circle circle;
    Rectangle rectangle;

    // Storing the address of circle
    shape = &circle;

    // Call circle draw function
    shape->draw();

    // Storing the address of rectangle
    shape = &rectangle;

    // Call rectangle draw function
    shape->draw();

    return 0;
}
```
Output will be like:
```
Drawing a circle
Drawing a rectangle
```