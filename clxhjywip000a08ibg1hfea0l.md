---
title: "My 100 Days Of Coding Challenge ( Week 3 Summary): Exploring Dart"
datePublished: Sun Jun 16 2024 12:58:49 GMT+0000 (Coordinated Universal Time)
cuid: clxhjywip000a08ibg1hfea0l
slug: my-100-days-of-coding-challenge-week-3-summary-exploring-dart
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/SyYmXSDnJ54/upload/33082d80396faae05f5c0b9f934c8f84.jpeg
tags: dart, dart-programming-tutorial, dart-for-beginners

---

In week two, we learnt about Dart's collections, exploring lists, sets, and maps. As we move into week three, we will shift our focus to understanding records and functions. Let's dive into these topics and uncover their intricacies.

## Records

Records are an anonymous, immutable, aggregate type in Dart. Unlike other collections, records allow you to bundle different types of values into a single entity, enabling structured grouping of data without defining a full class.

### Record syntax

Record expressions in Dart are comma-delimited lists enclosed in parentheses. Each element in the list can be of a different type, allowing you to bundle multiple values together in a single, structured entity.

For records with positional fields

```dart
var record = ('Edwin',30,true);
```

For records with named fields

```dart
var record = (name: "Edwin", age: 23, isActive : true);
```

Records can be a list of named or positional fields and it is written as so

```dart
var record = (name: 'Edwin', 20, true, 'Happy');
```

Record type annotation are comma-delimited and enclosed in parentheses. Record type annotation can be used to define the return type and parameter type. Let's see how this works.

```dart
(String, int) user((String, int) record){
  var (name, age) = record;

  return (name, age);
}
```

Fields in record expressions and type annotations work like parameters and arguments in functions. For positional fields, the fields go inside the parentheses:

```dart
// record type annotation in a variable declaration
(String, int) record;

// initialize it with a record expression
record = ('Kevin',22);
```

In record type annotations, named fields are placed inside curly braces. In a record expression, the names come before each field value, followed by a colon:

```dart
// record type annotation in a variable declaration
({String name, int age}) record;

// initialize it with a record expression
record = (name: 'Kevin', age: 23);
```

### Record fields

Record fields are accessible through built-in getters. Records are immutable, so fields do not have setters. Named fields have getters with the same name. Positional fields have getters named `$<position>`, skipping named fields:

```dart
  var record = (name: 'Edwin', 20, true, 'Happy');

  print(record.$1); // prints 20
  print(record.$2); // prints true
  print(record.$3); // prints Happy
  print(record.name); // prints Edwin
```

### Record types

There is no type declaration for individual record types. Records are structurally typed based on the types of their fields. Each field in a record has its own type.

```dart
(Object, num) record = ('Andrew', 30);
 
print(record.$1); // static type 'object', runtime type 'String'.
print(record.$2); // static type 'num', runtime type 'int'.
```

### Multiple returns

Records allow functions to return multiple values bundled together. To get the values from a returned record, [destructure the values](https://dart.dev/language/patterns#destructuring) into local variables using [pattern matching.](https://dart.dev/language/patterns#destructuring-multiple-returns)

What is pattern matching?

Pattern matching checks a sequence of tokens for a specific pattern. It identifies if a pattern exists in data in a structured and readable way. This technique is powerful for extracting data from complex structures and handling data types like lists, records, and custom types intuitively.

```dart
// return multiple values in a record
(String name, int age) userInfo(Map<String, dynamic> json) {
  return (json['name'] as String, json['age'] as int);
}

final json = <String, dynamic>{
     'name': 'Kevin',
     'age': 10,
  };

// Destructures using a record pattern with positional fields:
var (name, age) = userInfo(json);
```

## Functions

In Dart, functions are first-class objects and have a type, [Function](https://api.dart.dev/stable/3.4.4/dart-core/Function-class.html). This means that functions can be assigned to variables, passed as arguments to other functions, and returned from other functions. This feature allows for a high degree of flexibility and reuse in your code.

How to implement a function

```dart
void sayHello(){
    print("Hello, World");
}
```

For functions that contain just one expression, you can use a shorthand syntax:

```dart
void sayHello() => print("Hello, World");
```

The =&gt; expr syntax is a shorthand for { return expr; }. This notation is sometimes called *arrow* syntax.

### Parameters

Parameters are variables defined in the function signature that act as placeholders for the values that the function will operate on. They specify what kind of input the function expects.

In Dart, a function can have any number of *required positional* parameters. These can be followed by either *named* parameters or *optional positional* parameters, but not both.

### Named parameters

Named parameters are optional unless explicitly marked as required. When defining named parameters, use {param1, param2, ...}. If you don't provide a default value or mark a named parameter as required, their types must be nullable since their default value will be null:

```dart
void printPersonalInfo({String? name, int? age}) {
  if (name != null && age != null) {
    print("Name: $name Age: $age");
  } else{
    print("Either name or age is not provided");
  }
}
```

When calling a function, you can specify named arguments using paramName: value. For example:

```dart
printPersonalInfo(name: "John", age: 30);
```

To set a default value for a named parameter other than null, use = to specify the default value. The value must be a compile-time constant. For example:

```dart
void printPersonalInfo({String name = "Andrew", int age = 23}){
    print("Name: $name Age: $age");
}
```

If you want a named parameter to be mandatory, requiring callers to provide a value for the parameter, annotate it with required:

```dart
void printPersonalInfo({required String name, int? age}) {
  if (age != null) {
    print("Name: $name Age: $age");
  } else{
    print("Age is not provided");
  }
}

printPersonalInfo(name: 'Andrew'); // prints Age is not provided 😅
```

If you try to call the function printPersonalInfo without providing the name value, the analyzer throws an error.

### Optional positional parameters

Enclosing function parameters in \[ \] makes them optional positional parameters. Without a default value, their types must be nullable to accommodate null as the default value.

```dart
void main() {
  describePerson('Alice', 30, 'New York');  // All parameters provided
  describePerson('Bob', 25);  // Only name and age provided
  describePerson('Charlie');  // Only name provided
}

void describePerson(String name, [int? age, String? city]) {
  print('Name: $name');
  if (age != null) {
    print('Age: $age');
  } else {
    print('Age: not provided');
  }
  if (city != null) {
    print('City: $city');
  } else {
    print('City: not provided');
  }
}
```

Every Dart app must have a top-level main() function, which serves as the entry point. The main() function returns void and optionally accepts a List&lt;String&gt; parameter for arguments.

Here is a simple example:

```dart
void main(){
    print("Hello, World");
}
```

### Functions as first-class objects

A function can be passed as a parameter to another function. For example:

```dart
  var list = [1, 2, 3, 4, 5];

  list.forEach(print);
```

### Anonymous functions

you can also create functions without names. These functions are called *anonymous functions*, *lambdas*, or *closures*.

An anonymous function is similar to a named function and includes:

* Zero or more parameters, separated by commas
    
* Optional type annotations within parentheses
    

```dart
var list = [1, 2, 3];

list.forEach((item){
        print(item*2); 
    }
);

// output
// 2
// 4
// 6
```

### Generators

When you need to produce a sequence of values lazily, consider using a *generator function*. Dart has built-in support for two kinds of generator functions:

* **Synchronous** generator: Returns an Iterable object.
    
* **Asynchronous** generator: Returns a stream object.
    

To create a synchronous generator function in Dart:

1. Mark the function body with sync\*.
    
2. Use yield statements to produce values.
    

```dart
Iterable<int> count(int num) sync* {
  for (int i = 1; i <= num; i++) {
    yield i;
  }
}
```

To create an asynchronous generator function in Dart:

1. Mark the function body with sync\*.
    
2. Use yield statements to asynchronously produce values.
    

```dart
Stream<int> asyncCount(int num) async* {
  for (int i = 1; i <= num; i++) {
    yield i;
  }
}
```

In summary, week three of the 100 Days of Coding Challenge we learnt the intricacies of Dart's records and functions. By understanding records, we learned how to bundle different types of values into a single, structured entity. We explored the flexibility of Dart functions, including parameters, named and optional positional parameters, and the concept of functions as first-class objects. Additionally, we touched upon anonymous functions and generator functions for creating sequences of values lazily. This week's exploration has equipped us with essential tools and concepts, paving the way for more advanced topics in the upcoming weeks.