---
title: "My 100 Days Of Coding Challenge ( Week 4 Summary): Exploring Dart"
seoTitle: "Week 4: Exploring Dart in Coding Challenge"
seoDescription: "Week 4 of my 100 Days of Coding Challenge: Exploring control flows, loops, and exception handling in Dart. Dive in and enhance your coding skills"
datePublished: Mon Jul 01 2024 11:58:29 GMT+0000 (Coordinated Universal Time)
cuid: cly2xf3ai00000ajr3zop59jy
slug: my-100-days-of-coding-challenge-week-4-summary-exploring-dart
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/cckf4TsHAuw/upload/2963d18555c8fceba2bff96840f7b04f.jpeg
tags: dart, flutter, 100daysofcode, dart-programming-tutorial, dart-for-beginners

---

First, I apologize for not updating the series last week. I was on a trip across the Eastern part of my country, Uganda, and couldn't find time to write. But now I'm back home as you read this. Today, I will talk about control flows in Dart.

## Control flow

When we dive into programming, one of the basic concepts we encounter is control flow. Control flow is the order in which individual statements, instructions, or function calls are executed or evaluated. Understanding how control flow works in a programming language is essential for writing efficient, readable, and maintainable code.

At its core, control flow dictates how a program makes decisions, loops through instructions, and handles different execution paths. Just as a map provides directions for a journey, control flow constructs guide the program's execution path, allowing it to respond to various inputs and conditions dynamically.

In this article, we'll explore the primary control flow mechanism of loops. I will show you how to control the flow of your Dart code using loops and supporting statements:

* for loops
    
* while and do-while loops
    
* break and continue
    

You can also control the flow in Dart using:

* Branching statements like if and switch
    
* Exception handling with try, catch, and throw
    

## Loops

### For loops

The `for` loop is an essential tool for executing a block of code multiple times. Whether you need to iterate over a range of numbers, traverse a list, or repeat an action a specific number of times, the `for` loop provides a clear and concise way to do this.

### Basic Syntax of the for Loop

The basic structure of a `for` loop in Dart consists of three parts: initialization, condition, and increment/decrement expression. Here’s the general syntax:

```dart
for (initialization; condition; increment/decrement) {
  // code to be executed
}
```

* `Initialization:` This part runs once at the start of the loop. It’s usually used to declare and set up a loop control variable.
    
* `Condition:` Before each iteration, this condition is checked. If it’s true, the loop body runs. If it’s false, the loop stops.
    
* `Increment/Decrement:` This expression runs after each loop iteration. It’s typically used to update the loop control variable.
    

### Example

This is a simple example where we print numbers from 1 to 5:

```dart
for(int i = 1; i <= 5; i++){
    print(i);
}
```

In this example, the loop starts with `i` being initialized to 1. The condition `i <= 5` means that as long as `i` is less than or equal to 5, the loop continues to execute. The last part increments `i` by 1.

### for - in loop

Dart provides a convenient way to iterate over collections with the `for-in` loop. Here’s an example:

```dart
  List<String> names = ['Kevin', 'Andrew', 'John', 'Sid'];

  for (var name in names) {
    print(name);
  }
// output
// Kevin
// Andrew
// John
// Sid
```

### Understanding Closures and Index Capturing in Dart's for Loops

When working with for loops in Dart, a common confusion arises with closures capturing the loop variable (the index). To understand this concept better, let's break it down step by step.

### What is a Closure?

A closure is a function that captures variables from its surrounding scope. This means the closure "remembers" the values of the variables when it was created, even if those variables change later.

### Note

In Dart, when you create a closure inside a `for` loop, the closure captures the loop variable (index) by reference, not by value.

An example is below

```dart
void main(List<String> args) {
  var functions = <Function>[];

  for (var i = 0; i < 3; i++) {
    functions.add(() => print(i));
  }

  for (final f in functions) {
    f();
  }
}
// 0 1 2 output
```

### while loop

The `while` loop repeatedly runs a block of code as long as a given condition is true. The condition is checked before the loop body is executed, so the loop body may not run at all if the condition is false from the start.

Syntax:

```dart
while (condition) {
  // Code to be executed
}
```

Example:

```dart
void main() {
  int counter = 1;

  while (counter <= 5) {
    print('Counter: $counter');
    counter++;
  }
}
// Output
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
```

### do-while

The `do-while` loop is similar to the `while` loop, but with one key difference. The condition is checked after the loop body is executed. This means the loop body will always run at least once, regardless of whether the condition is initially true or false.

Syntax:

```dart
do {
  // Code to be executed
} while (condition);
```

Example:

```dart
void main() {
  int counter = 1;

  do {
    print('Counter: $counter');
    counter++;
  } while (counter <= 5);
}
// Output
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
```

## Break and continue

In programming, the `break` and `continue` statements are used to change the flow of loops (for, while, and do-while loops). Knowing how to use these statements well can help you write more controlled and readable code.

### The break Statement

The `break` statement is used to immediately end the nearest enclosing loop. When a `break` statement is encountered inside a loop, the loop stops, and the program continues with the next statement after the loop.

Syntax:

```dart
break;
```

Example:

```dart
void main() {
  for (int i = 1; i <= 10; i++) {
    if (i == 5) {
      break;
    }
    print(i);
  }
  print('Loop exited');
}
// Output
1
2
3
4
Loop exited
```

### The continue Statement

The `continue` statement skips the rest of the code inside the current iteration of the loop and moves on to the next iteration. It doesn't end the loop but jumps to the next cycle, ignoring the remaining code in the current loop iteration.

Syntax:

```dart
continue;
```

Example:

```dart
void main() {
  for (int i = 1; i <= 10; i++) {
    if (i % 2 == 0) {
      continue;
    }
    print(i);
  }
}
// Output
1
3
5
7
9
```

## Branching

Branching statements allow a program to make decisions and execute different code paths based on certain conditions. In Dart, the primary branching statements and elements are if and switch.

### if

The `if` statement is used to execute a block of code if a specified condition is true.

Syntax:

```dart
if (condition) {
  // Code to be executed if the condition is true
}
```

Example:

```dart
void main() {
  int number = 10;

  if (number > 0) {
    print('$number is positive');
  }
}
// Output
10 is positive
```

### Switch statement

The `switch` statement is used to execute one of many possible blocks of code based on the value of an expression. It is often more readable than using multiple `else if` statements when you need to handle many possible values.

Syntax:

```dart
switch (expression) {
  case value1:
    // Code to be executed if expression == value1
    break;
  case value2:
    // Code to be executed if expression == value2
    break;
  // More cases as needed
  default:
    // Code to be executed if no case matches
}
```

Example:

```dart
void main() {
  String grade = 'B';

  switch (grade) {
    case 'A':
      print('Excellent');
      break;
    case 'B':
      print('Good');
      break;
    case 'C':
      print('Fair');
      break;
    case 'D':
      print('Poor');
      break;
    case 'F':
      print('Fail');
      break;
    default:
      print('Invalid grade');
  }
}
// Output
Good
```

## Errors and Exceptions

Errors and exceptions are similar concepts, but they have a key difference. Exceptions are conditions that can be caught and handled by your program, while errors are typically issues that are not meant to be caught.

An exception occurs when your program encounters an unexpected situation, such as a file not being found or an invalid input that the program can anticipate and manage. For example, if a function expects a number between 1 and 100 and you provide a number outside this range, an exception can be raised and handled appropriately.

On the other hand, errors are usually more severe issues that arise from programming mistakes or system failures, such as syntax errors or out-of-memory errors. These are not meant to be caught by your program.

Let's go through how to work with this. I will introduce new concepts like classes, constructors, and Futures. Don't worry, I will explain them so you can understand everything we are going to learn.

### Throwing in class constructors

We can catch exceptions in class constructors. Constructors are special functions that create instances of classes. We will create a class called `Person` with an instance variable `age`. Then, we will check if the age entered by the user is within the acceptable range. If the age is not within the acceptable range then we can catch the exception. Let us go to the code.

```dart
class Person {
  final int age; // instance variable

  Person({required this.age}) {
    // checking the range that is acceptable for the program
    if (age < 0) {
      throw Exception("Age should not be negative");
    } else if (age > 140) {
      throw "Age should be less than 140";
    }
  }
}
```

Let me explain what is happening in the code above, especially the keyword `throw.` The `throw` keyword is used to indicate that an error has occurred. When you use `throw`, it creates an exception, signaling that something unexpected happened and the normal flow of the program should be interrupted. You can use `throw` to create an exception with any type of object.

Let's create a method that calls the `Person` class. We will then call this method in the main function. Here's how we will create the method:

```dart
void tryCreatingPerson({required int age}) {
  try {
    print(Person(age: age).age); // print the age
  } catch (e) {
    print(e.runtimeType);
    print(e);
  }
  print('----------------------');
}
```

We defined a method `tryCreatingPerson` that takes in a named parameter of age which must be an integer. The code inside the try-catch block is executed. If an exception occurs the control flow is then transferred to catch block.

`print(Person(age: age).age);` This line attempts to create an instance of the `Person` class with the provided `age` and then prints the `age` property of the created `Person` object.

`catch (e) { ... }` If an exception occurs in the `try` block, it is caught here, and the code inside the `catch` block is executed.

* `print(e.runtimeType);` This prints the type of the exception that was caught.
    
* `print(e);` This prints the exception message or object itself.
    

Inside the catch block, you can pass another argument like this: `catch(error, stackTrace) {...}`. The new concept here is `stackTrace`. The `error` is similar to what we encountered before as `e`, so don't worry much about it. So, what does `stackTrace` do?

the `stackTrace` provides a trace of the function calls that were active at the time an exception was thrown. It shows the sequence of function calls leading up to the point where the error occurred, which can be extremely useful for debugging. This is how stackTrace looks like.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1719831525199/758d62d1-5574-4714-8365-7f7ff4693204.png align="center")

Let us go to the main function and then call the `tryCreatingPerson` method.

```dart
void main(List<String> args) {
  tryCreatingPerson(age: 30);
  tryCreatingPerson(age: -1);
  tryCreatingPerson(age: 150);
}
```

This `main` function calls the `tryCreatingPerson` function three times with different `age` values: 30, -1, and 150. Each call will produce different outputs. Go ahead and run the code. I'll be here .

### Custom exception class

We are going to use the same example we have worked with before but only tweak some few changes with our code. First let us create a custom exception class that we will define. We are calling it `InvalidAgeException` that will implement Dart's Exception class.

```dart
class InvalidAgeException implements Exception {
  final int age;
  final String message;

  InvalidAgeException(this.age, this.message);

  @override
  String toString() => 'InvalidAgeException: $message $age';
}
```

So, what this does is it takes in the age and the message that explains the type of error or its cause, then returns it as a string. Let us go to the `tryCreatingPerson` and tweak some changes from there.

```dart
void tryCreatingPerson({required int age}) {
  try {
    print(Person(age: age).age);
  } on InvalidAgeException catch (exceptions, stackTrace) {
    print(exceptions);
    print(stackTrace);
  }
  print('----------------------');
}
```

`on InvalidAgeException catch (exceptions, stackTrace) { ... }` This block catches exceptions of type `InvalidAgeException`.

* `print(exceptions);` Prints the exception itself, which usually includes a message.
    
* `print(stackTrace);` Prints the stack trace, which shows the sequence of function calls that led to the exception.
    

Then we alse tweak the Person class by introducing the `InvalidAgeException` class. Like so.

```dart
class Person {
  final int age;

  Person({required this.age}) {
    if (age < 0) {
      throw InvalidAgeException(age, "Age should not be negative");
    } else if (age > 140) {
      throw InvalidAgeException(age, "Age should be less than 140");
    }
  }
}
```

This will throw the custom exception class we created. Then go ahead in the main function.

```dart
void main(List<String> args) {
  tryCreatingPerson(age: 30);
  tryCreatingPerson(age: -1);
  tryCreatingPerson(age: 150);
}
```

This time the errors will be coming from our own made exception class. Cool right!.

## Note:

I found Vandad Nahavandipoor's YouTube tutorial series "[Dart Crash Course](https://youtube.com/playlist?list=PL6yRaaP0WPkVLSOchfoIA0ZXySz4eSYV2&si=VTG2JrRX-Adv-kbg)" to be incredibly helpful in understanding various concepts of Dart programming. His detailed explanations and practical examples were instrumental in the completion of this article.

In conclusion, understanding control flow in Dart is fundamental for writing efficient and maintainable code. By mastering loops, branching statements, and exception handling, we can create dynamic and responsive programs. Whether we're iterating over collections with for loops, making decisions with if and switch statements, or managing errors with try, catch, and throw, these control flow mechanisms are essential tools in our Dart programming toolkit. As we continue our coding journey, let's keep experimenting with these concepts to deepen our understanding and enhance our coding skills. Till we meet again. Happy coding!