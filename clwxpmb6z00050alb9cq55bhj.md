---
title: "My 100 Days of Coding Challenge(Week 1 Summary): Exploring Dart"
datePublished: Sun Jun 02 2024 15:41:35 GMT+0000 (Coordinated Universal Time)
cuid: clwxpmb6z00050alb9cq55bhj
slug: my-100-days-of-coding-challengeweek-1-summary-exploring-dart
canonical: https://x.com/ayikoandrew_/status/1797285321106653213
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1717342217606/d914da5b-ea85-4e0f-be5a-eb78602aede6.png
tags: dart, dart-programming-tutorial, dart-for-beginners

---

As part of my 100 days of coding challenge, I've been diving into Dart, a client-optimized language for developing fast apps on any platform. In this article, I'll summarize what I've learnt about Dart in the first week of the challenge, its features.

# **What is Dart?**

Dart is a programming language designed for building mobile, desktop, server, and web applications. It's known for its:

1. **Type Safety**: Dart uses static type checking to ensure that a variable’s value always matches its static type. Types are mandatory, but type annotations are optional.
    
2. **Null Safety**: Dart has built-in sound null safety, meaning values can’t be null unless explicitly stated.
    
3. **Flexible Execution Runtime**: Dart is paired with a flexible execution runtime platform, making it the foundation for Flutter.
    

# **Key Features of Dart**

#### **Type Safety**

Dart ensures type safety through static type checking. This means that you don't always have to explicitly state the type of a variable, Dart can infer it based on usage.

```dart
var name = 'Andrew'; // Dart infers that 'name' is of type String
```

#### **Null Safety**

Dart's sound null safety prevents null dereference errors by ensuring that non-nullable variables cannot hold null values.

```dart
String? nullableName; // Nullable type
String nonNullableName = 'Alice'; // Non-nullable type
```

## **The Platform**

### **Native Platform**

For mobile and desktop applications, Dart uses both a Just-In-Time (JIT) compiler during development and an Ahead-Of-Time (AOT) compiler for deployment. JIT allows for features like hot reload, which speeds up the development process.

```dart
void main() {
  print('Hello, Dart!');
}
```

When ready for deployment, the AOT compiler compiles Dart to native ARM or x64 machine code, ensuring fast startup times and efficient memory management.

### **Web Platform**

Dart can also be compiled to JavaScript or WebAssembly, making it versatile for web development. It supports:

* **Incremental JavaScript Compiler**: For a fast developer cycle.
    
* **Optimized JavaScript Compiler**: For compact and efficient JavaScript code.
    
* **WebAssembly Compiler**: For high-performance applications.
    

## **Memory Management and Isolates**

Dart's runtime handles memory management using a generational garbage collector, ensuring efficient memory usage. It also manages isolates—independent memory heaps used to run Dart code concurrently.

## **Using Final and Const**

If you want to create immutable variables, use final or const.

```dart
final String name = 'Andrew';
const int age = 30;
```

final is for variables that are set once and can change at runtime, while const is for compile-time constants

## **Late Variables**

The late keyword is used for non-nullable variables that are initialized after their declaration or for lazy initialization.

I am excited to dive deep into Dart in the coming week . For more information you can use the [dart documentation](https://dart.dev/language) which I am highly utilizing. Stay tuned for my insights and experiences as I explore this powerful language.