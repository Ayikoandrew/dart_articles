---
title: "100 Days Of Coding Challenge ( Week 2 Summary): Exploring Dart"
seoTitle: "Week 2 Coding: Dart Exploration Summary"
datePublished: Sat Jun 08 2024 09:01:19 GMT+0000 (Coordinated Universal Time)
cuid: clx5vyoaq00040ajv79kbfdj8
slug: 100-days-of-coding-challenge-week-2-summary-exploring-dart
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1717830727801/7bf0be23-a2cd-4bc2-a5dc-1034a18768d5.png
tags: dart-programming-tutorial, dart-for-beginners

---

Last week, I began the 100 Days of Coding challenge. I have documented my progress in a summary, which you can read [here](https://ayikoandrew.hashnode.dev/my-100-days-of-coding-challengeweek-1-summary-exploring-dart). This week, I plan to write a couple of articles, and this is the first of the many I have planned for week 2. Let's dive into week two's study.

## Collections

Dart has ready-to-use implementations and features for working with common data structures such as lists, sets and maps.

Now let us look at each of the following starting with lists.

## Lists

The most common collection in nearly every programming language is the array, or ordered group of objects. In Dart, arrays are known as List objects.

Dart lists are denoted by a common separated list of expressions or values, enclosed in square brackets(\[\]).

In Dart you can create a list using the List class. Lists in Dart are zero-based, meaning the index of the first element is 0 and list.length-1 is the index of the last value. You can get a list’s length using the .length property.

```dart
List<int> numbers = [1, 2, 3, 4, 5];
```

To create a list that is a compile-time constant, add const before the list literal.

```dart
var constantList = const [1, 2, 3];
```

## Sets

A set is an unordered collection of unique items. Dart provides a Set class for this purpose. Sets are useful when you need to ensure that no duplicates are present in your collection. A set is declared as so.

```dart
Set<String> names = {"Andrew", "Kevin", "Jude"};
```

### Note:

```dart
var name = {"Andrew", "Kevin", "Jude"};
```

Dart infers that name has the type set Set&lt;String&gt;. If you try to add the wrong type of value to the set, the analyzer or runtime raise an error.

To create an empty set, use {} preceded by a type argument, or assign {} to a variable of type set.

```dart
var names = <String> {};
```

or

```dart
Set<String> names = {};
```

But

```dart
var names = {}; // creates a map not a set
```

Add items to an existing set using the add() or addAll() method:

```dart
var names = <String>{};
names.add('Jude')
names.addAll({"Andrew", "Kevin"});

// Or

// This uses cascade Notation (Which will be in the next article)
var names = <String>{}
    ..add('Jude')
    ..addAll({'Andrew', 'Kevin'});
```

Use .length to get the number of items in the set.

```dart
print(names.length); // prints 3
```

To create a set that’s a compile-time constant, add const before the set literal

```dart
final constantSet = const {"Andrew", "Jude","Carol"};
```

## Maps

A map is a collection of key-value pairs, where each key is unique. Dart uses the Map class to represent maps. Maps are useful for looking up values by their associated keys. Both keys and values can be any type of object. Each key occurs only once, but you can use the same value multiple times.

```dart
  var gifts = { 
  // key: value
  'first': 'Happy',
  'second':'turle doves'
  };
```

Dart infers that gifts has the type Map&lt;String, String&gt;. If you try to add the wrong type of value to either map, the analyzer or runtime raises an error.

Add a new key-value pair to an existing map using the subscript assignment operator (\[\]=):

```dart
var gifts = {"first": 'partridge'};
gifts['fourth'] = 'calling birds';
```

Retrieve a value from a map using the subscript operator

```dart
var gifts = {'first': 'partridge'};

print(gifts['first']);
```

If you look for a key that isn’t in the map, you get null in return

use .length to get the number of key-value pairs in the map

```dart
var gifts = {'first': 'partridge'};
print(gifts.length); // 1
```

To create a map that is a compile-time constant, add const before the map literal

```dart
var gifts = const {'first': 'partridge'};
```

## Operators

### Spread operators

Dart supports the spread operator (…) and the null-aware spread operator(…?) in list, map, and set literals. Spread operators provide a concise way to insert multiple values into a collection.

For example, you can use the spread operator(…) to insert all the values of a list into another list.

```dart
var list = [1, 2, 3];
var list2 = [0, ...list];
print(list2)
```

If the expression to the right of the spread operator might be null, you can avoid exceptions by using a null-aware spread operator (…?)

```dart
List<int>? list = [1, 2, 3];
var list2 = [0, ...?list];
print(list2);
```

## Generics

Generics in Dart allow you to write flexible, reusable code by creating classes, methods and functions that can work with different data types without sacrificing type safety.

### Why use generics?

Generics are often required for type safety, but they have more benefit than just allowing your code to run.

* Write reusable code: You can write a single class, method, or function that works with different data types.
    
* Improve code readability and maintainability: Generic code is often cleaner and easier to understand.
    

### Using Generics in Dart

Please don't worry about the classes, this is intended purely for study purposes.

### Generic class

We can define a class to work with different data types using generics.

```dart
class Creature<T> {
T? name;

Creature(this.name);

void setName(T newName) => name = newName;

T? getName() => name;

}
```

In this example, Creature is a generic class with a type parameter T. We can create instance of Creature with different types such as int and String

### Generic methods

We can also define generic methods within a class or as standalone function

```dart
T? getCreatures<T> (List<T> creatures) {
    if(creatures.isNotEmpty){
	      return creatures.first;
     }
     return null;
}
```

That is a wrap.

In conclusion, exploring Dart's collections, such as lists, sets, and maps, has provided valuable insights into handling data structures effectively. Lists offer a flexible way to manage ordered groups of objects, sets ensure the uniqueness of elements in an unordered collection, and maps allow efficient key-value pair management. These fundamental concepts are crucial for building efficient and error-free applications in Dart. As I continue my 100 Days of Coding Challenge, I look forward to discovering more features and capabilities of Dart, including records, built-in types, and patterns, which will further enhance my understanding and proficiency in this versatile language. Stay tuned for the next article where I will dive deeper into these exciting topics.