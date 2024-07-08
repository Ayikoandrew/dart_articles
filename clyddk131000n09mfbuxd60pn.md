---
title: "100 Days Of Coding Challenge ( Week 5 Summary): Exploring Dart"
seoTitle: "Week 5: Dart Highlights in 100 Days of Code"
seoDescription: "Week 5 of 100 Days of Coding Challenge: Diving into Dart classes, constructors, and methods"
datePublished: Mon Jul 08 2024 19:27:55 GMT+0000 (Coordinated Universal Time)
cuid: clyddk131000n09mfbuxd60pn
slug: 100-days-of-coding-challenge-week-5-summary-exploring-dart
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/xG8IQMqMITM/upload/ab931776d1bb021d79d721a9592b83e2.jpeg
tags: dart-programming-tutorial, dart-language, dart-for-beginners

---

Last week, I explored loops, branching, and exception and error handling in depth. This week, I covered a lot and will be discussing classes, constructors, and methods. Let us start today's class.

## Classes

A class is a blueprint of an object. Every object is an instance of a class, and all classes except `Null` descend from `Object`. Let me explain this with some code.

```dart
void main() {
  // Creating an instance of the Person class
  Person p = Person('Alice', 30);

  // Calling the method
  p.introduce(); // Output: Hi, I am Alice and I am 30 years old.
}


class Person {
  String name;
  int age;

  // Constructor
  Person(this.name, this.age);

  // Method
  void introduce() {
    print('Hi, I am $name and I am $age years old.');
  }
}
```

In this example

* `Person` is a class, which serves as a blueprint for creating `Person` object.
    
* `p` is an instance (object) of the `Person` class.
    
* The `Person` class extends the `Object` class implicitly.
    

## Defining a Class

A class in Dart is defined using the `class` keyword, followed by the class name and the body of the class enclosed in curly braces `{}`.

```dart
class Person {
  String name;
  int age;

  // Constructor
  Person(this.name, this.age);

  // Method
  void introduce() {
    print('Hello, my name is $name and I am $age years old.');
  }
}
```

### Creating an Instance

To create an instance of a class, just call the constructor directly.

```dart
void main() {
  var person1 = Person('Alice', 30);
  person1.introduce();

  // in Dart the 'new' keyword is optional
  var person2 = Person('Bob', 25);
  person2.introduce();
}
```

## Constructors

Now it is a good time to talk about constructors. A constructor is a special method that is called when an object is instantiated. It is used to initialize object's properties. Constructors can be defined using a syntax similar to method declarations, but without a return type and using the class name as the method name.

## Types of constructors

### Generative constructors

Generative constructor is a standard constructor in Dart when called it generates a new instance of the class every time it is called. To instantiate a class use generative constructor.

```dart
class Vector {
    final int x;
    final int y;
    // Generative constructor with initializing formal parameters:
    Vector(this.x, this.y);
}
```

### Default constructors

Dart uses the default constructor when you have not declared a constructor. The default constructor is a generative constructor without arguments or a name.

### Named constructors

Named constructors allow you to create multiple constructors for a class with different names, providing extra clarity.

```dart

class Vector {
    final int x;
    final int y;
    // Generative constructor with initializing formal parameters:
    Vector(this.x, this.y);
    
    // Named constructor with points at the origin
    Vector.origin() 
                  : x = 0, 
                    y = 0;

    @override
    String toString() => '$x $y ';
}
```

### Constant constructors

If your class creates unchanging objects, make these objects compile-time constants. To do this, define a `const` constructor with all instance variables set as `final`.

```dart
class Point {
  static const Point origin = Point(0, 0);

  final double x, y;

  const Point(this.x, this.y);
}
```

### Redirecting constructors

A constructor might redirect to another constructor in the same class. A redirecting constructor has an empty body and uses `this` instead of the class name after a colon (:).

```dart
class Vector {
    final int x;
    final int y;
    // Generative constructor with initializing formal parameters:
    Vector(this.x, this.y);
     
    // Redirecting constructor that redirects to the generative constructor.
    Vector.origin() : this(4, 0);
                  

    @override
    String toString() => '$x $y ';
}
```

### Factory constructors

When dealing with the following two cases for implementing a constructor, use the `factory` keyword:

* The constructor doesn't always create a new instance of its class. Although a factory constructor cannot return `null`, it might return:
    
    * an existing instance from a cache instead of creating a new one
        
    * a new instance of a subtype
        
* You need to perform complex tasks before creating an instance. This could include checking arguments or doing other processing that cannot be handled in the initializer list.
    

```dart
class Logger {
  static final Logger _instance = Logger._internal();

  // Private constructor
  Logger._internal();

  // Factory constructor
  factory Logger() {
    return _instance;
  }

  void log(String message) {
    print(message);
  }
}
```

## Instance methods

An instance method is a method that works on instances of a class. Instance methods can access and modify the instance variables (fields) of the class. They usually operate on the data within a specific instance of the class and can use the `this` keyword to refer to the current instance.

```dart
class Rectangle {
  double width;
  double height;

  // Constructor
  Rectangle(this.width, this.height);

  // Instance method to calculate the area
  double area() {
    return width * height;
  }

  // Instance method to calculate the perimeter
  double perimeter() {
    return 2 * (width + height);
  }

  // Instance method to display dimensions
  void display() {
    print('Width: $width, Height: $height');
  }
}
```

## Getters and setters

Getters and setters are special methods that provide read and write access to an object's properties. You can create additional properties by implementing getters and setters, using the `get` and `set` keywords:

```dart
class Rectangle {
  double width;
  double height;

  // Constructor
  Rectangle(this.width, this.height);

  // getters
  double get getWidth => width;
  double get getHeight => height;

  // setters
  set setWidth(double value) => width = value;
  set setHeight(double value) => height = value;

  ...
}
```

In conclusion, this week’s exploration of Dart has provided a comprehensive understanding of classes, constructors, and methods. We covered various types of constructors, including generative, default, named, constant, redirecting, and factory constructors, each serving unique purposes in object instantiation and initialization. Additionally, we learned about instance methods, which operate on class instances, and getters and setters, which offer controlled access to object properties. As we continue this coding journey, these concepts will be instrumental in programs. Happy coding.