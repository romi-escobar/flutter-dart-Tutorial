## Data Type
Numbers (int, double)
Strings (String)
Booleans (bool)
Records ((value1, value2))
<br><br>

## List
`[List]` is a built-in collection types. It's a fundamental data structure used to store an ordered collection of objects. Lists are similar to arrays in other programming languages but are more flexible and versatile. They allow you to store elements of any data type. Lists are dynamic in size, meaning they can grow or shrink as needed.

**_Creating Lists_**: declaration and initialization
* **Using Literal Syntax:**
  ```dart
  // Implicitly declaring a List of integers
  var numbers = [1, 2, 3, 4, 5];
  // Explicitly declaring a List of strings
  List<String> names = ['Alice', 'Bob', 'Charlie'];
  ```
* **Using the List Constructor:**
  ```dart
  var numbers = List<int>.filled(5, 0); // Creates a list with 5 elements, all initialized to 0
  var names = List<String>.empty(growable: true); // Creates an empty growable list of strings
  ```

**_Accessing Elements:_** You can access elements in a List using square brackets `[]` and providing the index of the element. Indexing starts at 0
```dart
print(names[0]); // Outputs: Alice
```

**_Modifying Elements:_** You can modify elements in a List by assigning new values to specific indices.
```dart
names[0] = 'Alex'; // Changing 'Alice' to 'Alex'
```

**_List Methods_**: Some common methods include:
* `add()`: Adds an element to the end of the list.
* `addAll()`: Adds all elements of another iterable to the end of the list.
* `remove()`: Removes the first occurrence of a specified value from the list.
* `removeAt()`: Removes the element at a specified index.
* `contains()`: Checks if the list contains a specified value.
* `isEmpty` and `isNotEmpty`: Checks if the list is empty or not.

**_Iterating Over a List_**: You can iterate over a List using a variety of methods, including `for-in` loops, `forEach()` method, `map()` method, etc.
```dart
var numbers = [1, 2, 3, 4, 5];
for (var number in numbers) {
  print(number);
}
```
<br>

## Set
`{Set}` is a collection of unique elements that does not allow duplicate values. You don't care about the order of the elements and don't allow duplicates.  

**_Creating Sets_**: 
* **Using Literal Syntax:**
  ```dart
  var letters = {'a', 'b', 'c'};
  var numbers = {1, 2, 3, 4, 5};
  ```
* **Using the Set Constructor:**
  ```dart
  var fruits = Set<String>(); // Creates an empty Set of strings
  fruits.addAll(['apple', 'banana', 'orange']); // Adds elements to the set
  ```

**_Set Operations_**
* **Union**: Combines two sets into a new set containing all unique elements from both sets.
  ```dart
  var set1 = {'a', 'b', 'c'};
  var set2 = {'b', 'c', 'd', 'e'};
  var unionSet = set1.union(set2); // Output: {'a', 'b', 'c', 'd', 'e'}
  ```
* **Intersection**: Finds the common elements between two sets.
  ```dart
  var intersectionSet = set1.intersection(set2); // Output: {'b', 'c'}
  ```
* **Difference**: Finds the elements that are present in the first set but not in the second set.
  ```dart
  var differenceSet = set1.difference(set2); // Output: {'a'}
  ```

**_Set Properties_**
* **Length**: Returns the number of elements in the set.
  ```dart
  print(fruits.length); // Output: 3
  ```
* **isEmpty** and **isNotEmpty**: Check if the set is empty or not.
  ```dart
  print(fruits.isEmpty); // Output: false
  ```

**_Set Methods_**
* `add()`: Adds an element to the set.
* `addAll()`: Adds all elements from another iterable to the set.
* `remove()`: Removes the specified element from the set.
* `clear()`: Removes all elements from the set.
Checking for Elements:
* `contains()`: Checks if the set contains a specific element.
* `for-in` loop
* `forEach()`: Iterates over each element in the set and applies a function to each element.
<br><br>

## Maps
`Maps` are a collection of key-value pairs, where each key maps to a value. Maps are also known as dictionaries, hashmaps, or associative arrays in other programming languages.

**_Creating Maps_**
* **Using Map Literals:**
  ```dart
  var capitals = {
    'France': 'Paris',
    'Spain': 'Madrid',
    'Netherlands': 'Amsterdam',
  };
  ```
* **Using the Map Constructor:**
  ```dart
  var capitals = Map<String, String>();
  capitals['France'] = 'Paris';
  capitals['Spain'] = 'Madrid';
  capitals['Netherlands'] = 'Amsterdam';
  ```
* **Using the `from` Constructor for Creating a Map from Another Map:**
  ```dart
  var capitals = {
    'France': 'Paris',
    'Spain': 'Madrid',
  };
  var moreCapitals = Map.from(capitals);
  moreCapitals['Netherlands'] = 'Amsterdam'; // Adds a new key-value pair
  ```

**_Common Operations_**
* **Adding Key-Value Pairs:**
  ```dart
  capitals['Italy'] = 'Rome'; // Adds a new key-value pair
  ```
* **Updating a Value:**
  ```dart
  capitals['France'] = 'Lyon'; // Updates the value associated with the key 'France'
  ```
* **Removing a Key-Value Pair:**
  ```dart
  capitals.remove('Spain'); // Removes the key-value pair where the key is 'Spain'
  ```
* **Looking Up a Value:**
  ```dart
  print(capitals['France']); // Prints the value associated with the key 'France'
  ```
* **Checking for a Key or Value:**
  ```dart
  print(capitals.containsKey('Germany')); // Checks if the key 'Germany' exists
  print(capitals.containsValue('Madrid')); // Checks if the value 'Madrid' exists
  ```
* **Iterating Over a Map:**
  ```dart
  capitals.forEach((key, value) {
    print('The capital of $key is $value');
  });

    for (var key in capitals.keys) {
      print('Key: $key, Value: ${capitals[key]}');
    }
    ```

**_Properties_**
* **keys:** Returns an iterable object containing all keys in the map.
* **values:** Returns an iterable object containing all values in the map.
* **length:** Returns the number of key-value pairs in the map.
* **isEmpty / isNotEmpty:** Checks if the map is empty or not.

<br>

## Null
`null?` represents the absence of a value. It's used to indicate that a variable does not currently have any assigned value.   
To make a variable nullable, you append a `?` to its type. This tells Dart that the variable can hold either a value of its type or null.

**Default Initial Value:** If you declare a variable without assigning it a value, it will default to `null`.
```dart
int? number; // Declared but not assigned, defaults to null
```

**Assignment to Null:** You can explicitly assign a variable the value of `null` to indicate that it currently has no meaningful value.
```dart
String? name = null; // Assigning null to a variable
```

**Null Safety:** introduced in Dart 2.12, introduces strict null safety rules that help prevent null reference errors at runtime. Variables are non-nullable by default, and you must explicitly declare a variable as nullable if it can hold a null value.
  ```dart
  String? nullableName; // Nullable variable declaration
  String nonNullableName = 'John'; // Non-nullable variable declaration
  ```

**Checking for Null:** It's important to check for `null` before using a variable that could potentially be `null`, to avoid runtime errors. Dart provides several ways to safely handle null values, such as the null-aware operators `?.`, `??`, and `!`.
```dart
String? name;

// Using null-aware operators
print(name?.length); // Safe access, prints null if name is null
print(name ?? 'Unknown'); // Null coalescing operator, provides a default value if name is null
print(name!.length); // Asserts that name is not null, throws an exception if it is
```

**Conditional invocation:** allows you to call a method or access a property conditionally based on whether an object is null or not.1. 
* **Conditional Member Access (`?.`):** allows you to call methods or access properties on an object only if the object is not null. If the object is null, the entire expression evaluates to null, avoiding a null reference error.
  ```dart
  String? name;
  int? length = name?.length; // If name is not null, returns its length; otherwise, returns null
  ```

* **Null-aware Assignment (`??=`):** assigns a value to a variable only if the variable is currently null. If the variable is not null, it remains unchanged.
  ```dart
  String? name;
  name ??= 'John'; // Assigns 'John' to name only if name is null
  ```
* **Conditional Function Invocation (`?.()`):** allows you to call a method on an object conditionally. If the object is null, the method call is skipped, and the entire expression evaluates to null.
  ```dart
  String? greeting;
  print(greeting?.toUpperCase()); // Calls toUpperCase() only if greeting is not null
  ```
* **Null-aware Spread Operator (`...?`):** allows you to spread the elements of an iterable only if the iterable is not null. If the iterable is null, the spread operation is skipped.
  ```dart
  List<int>? numbers;
  List<int> doubledNumbers = [...?numbers ?? []]; // Spreads numbers if not null, otherwise uses an empty list
  ```
<br><br>

## Enum
`enum` allows you to define a type with a fixed set of constant values. enums are like a predefined list of options that you can use in your code to make it easier to work with and understand.
They are particularly useful for modeling concepts with a predefined set of options, such as colors, days of the week, or states of a process.  

**_Defining an Enumeration:_** use the `enum` keyword followed by the name of the enumeration and a list of constant values.
```dart
enum Color {
  red,
  green,
  blue,
}
```
**_Using an Enumeration:_** use the constants defined in an enumeration just like any other value. 
```dart
Color favoriteColor = Color.blue;
print(favoriteColor); // Output: Color.blue
```
**_Enumerations with Associated Values:_** enumerations can also have associated values
```dart
enum TrafficLight {
  red,
  yellow,
  green,
}

extension TrafficLightExtension on TrafficLight {
  String get description {
    switch (this) {
      case TrafficLight.red:
        return 'Stop';
      case TrafficLight.yellow:
        return 'Prepare to stop';
      case TrafficLight.green:
        return 'Go';
    }
  }
}

void main() {
  TrafficLight currentLight = TrafficLight.green;
  print(currentLight.description); // Output: Go
}
```
**_Using Enumerations in Switch Statements:_** to handle different cases based on the enumeration's value.
```dart
void printColor(Color color) {
  switch (color) {
    case Color.red:
      print('Red color');
      break;
    case Color.green:
      print('Green color');
      break;
    case Color.blue:
      print('Blue color');
      break;
  }
}

void main() {
  Color favoriteColor = Color.blue;
  printColor(favoriteColor); // Output: Blue color
}
```


Future and Stream: Used in asynchrony support.
Iterable: Used in for-in loops and in synchronous generator functions.
Never: Indicates that an expression can never successfully finish evaluating. Most often used for functions that always throw an exception.
void: Indicates that a value is never used. Often used as a return type.

