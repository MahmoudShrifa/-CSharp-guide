
## 🎓 C\# Beginner's Guide

**In-depth Explanations | Clear and Detailed Examples | Learn C\# from Scratch**

-----

### 🧠 1. Variables: The Foundation of Programming

At its core, a variable is a reserved memory location to store a specific type of data. Think of it as a labeled box where you can put things. C\# is a "strongly typed" language, which means you must specify the type of data a variable will hold before you can use it.

  * **Common Data Types Explained:**

      * `int`: Used for whole numbers (integers) like `10`, `-5`, or `1000`. It cannot store decimals.
      * `double`: The most common type for numbers with decimal points, like `3.14` or `99.99`. It's highly precise and a good default choice.
      * `float`: Also for decimal numbers, but it has less precision than `double` and is often used for memory-sensitive applications. You must add `F` at the end of the number, like `3.5F`.
      * `string`: Used for storing text, such as names, sentences, or phrases. Text values are always enclosed in double quotes `" "`.
      * `char`: Stores a single character, like `'A'` or `'1'`. Characters are enclosed in single quotes `' '`.
      * `bool`: A logical data type that can only hold one of two values: `true` or `false`. It's essential for making decisions in your code.
      * `decimal`: A more precise type for decimal numbers, mainly used for financial calculations where rounding errors must be avoided. You must add `M` at the end of the number, like `99.99M`.

-----

### 📝 2. Declaring and Initializing Variables

Before you can use a variable, you need to declare it (give it a type and name) and then initialize it (give it a value). You can do this in a single line.

**Syntax:** `DataType variableName = value;`

```csharp
// Declaring an integer variable named 'age' and setting its value to 25.
int age = 25;

// Declaring a string variable to store a person's name.
string fullName = "Mahmoud Sherif";

// A boolean variable to check if a user is online.
bool isUserOnline = true;

// You can use these variables in your code.
Console.WriteLine($"The user's name is {fullName}.");
Console.WriteLine($"He is {age} years old.");
```

-----

### 💬 3. Controlling Your Program's Output

The `Console` class is your main tool for displaying information to the user in the console window.

  * `Console.WriteLine()`: **(Write Line)** Prints the specified data to the console, and then moves the cursor to the next line. This is great for printing a series of messages, each on a new line.
  * `Console.Write()`: **(Write)** Prints the specified data to the console without moving to a new line. This is useful for building a single line of text or for prompting the user for input on the same line.

<!-- end list -->

```csharp
// This will print two separate lines.
Console.WriteLine("Hello, C# world!");
Console.WriteLine("This is a new line.");

// This will print "Hello, C# World!" all on one line.
Console.Write("Hello, ");
Console.Write("C# ");
Console.Write("World!");
```

-----

### 🧮 4. Performing Math Operations

C\# supports all standard mathematical operators. When performing division (`/`) with two integers, the result will always be an integer (the fractional part is truncated). To get a decimal result, you need to "cast" one of the numbers to a `double`.

```csharp
int a = 20;
int b = 3;

// Integer division: the result is 6, not 6.66
int result1 = a / b;

// To get the correct decimal result, we use casting.
// We tell the compiler to temporarily treat 'a' as a double.
double result2 = (double)a / b; // Result will be 6.666666...
```

-----

### 🔀 5. Increment and Decrement Operators

The increment (`++`) and decrement (`--`) operators are shortcuts for adding or subtracting 1 from a variable.

  * **Postfix (`i++`):** The value of `i` is used in the current expression, and **then** it's incremented.
  * **Prefix (`++i`):** The value of `i` is incremented **first**, and **then** the new value is used in the expression.

<!-- end list -->

```csharp
int counter1 = 5;
Console.WriteLine(counter1++); // Prints 5, then counter1 becomes 6.
Console.WriteLine(counter1);   // Now prints 6.

int counter2 = 5;
Console.WriteLine(++counter2); // counter2 becomes 6, then prints 6.
Console.WriteLine(counter2);   // Still 6.
```

-----

### 🔁 6. Understanding Type Conversion

Converting data from one type to another is a common task.

  * **Implicit Conversion:** This happens automatically when converting from a "smaller" data type to a "larger" one (e.g., from `int` to `double`). It's safe because there's no risk of losing data.
  * **Explicit Conversion (Casting):** This is required when converting from a larger type to a smaller one (e.g., from `double` to `int`). You must explicitly tell the compiler you're aware of the potential for data loss by using parentheses.

<!-- end list -->

```csharp
// Implicit: No data loss
int myInt = 10;
double myDouble = myInt; // OK, 10 is converted to 10.0

// Explicit: Potential data loss, requires casting
double mySecondDouble = 12.9;
int mySecondInt = (int)mySecondDouble; // Result is 12 (the .9 is lost)
```

-----

### 🔄 7. Converting Between Strings and Numbers

You can't do math with a number stored as a `string`. You need to convert it first.

  * **`string` to `int`**: Use `int.Parse()` or the safer `int.TryParse()`. `Parse` will throw an error if the string is not a valid number.
  * **`int` to `string`**: Use the `.ToString()` method. Every variable in C\# has this method.

<!-- end list -->

```csharp
// Converting a string to an integer
string ageText = "30";
int ageValue = int.Parse(ageText); // ageValue is now the number 30

// Converting an integer to a string
int price = 150;
string priceText = price.ToString(); // priceText is now the string "150"
```

-----

### ✨ 8. `var` Keyword: Let the Compiler Do the Work

`var` is a convenient keyword that tells the C\# compiler to automatically infer the data type of a variable based on the value you give it. This helps reduce code verbosity.

```csharp
var city = "Cairo";     // Compiler sees "Cairo" and knows 'city' is a string.
var population = 10000000;  // Compiler knows 'population' is an int.
var isActive = true;    // Compiler knows 'isActive' is a bool.
```

-----

### 🧵 9. Advanced String Formatting (String Interpolation)

String Interpolation is the most modern and readable way to embed variables directly into a string. You start the string with a dollar sign (`$`) and place your variables inside curly braces `{}`.

```csharp
string productName = "Laptop";
double price = 1200.50;

// The old way: less readable
string messageOld = string.Format("The {0} costs ${1}", productName, price);

// The modern, better way:
string messageNew = $"The {productName} costs ${price}.";
```

-----

### 🧮 10. Working with Numbers and Money

C\# offers various formatting options to display numbers, percentages, and currency in a clean way. You use format specifiers inside the curly braces.

  * `{0:N}`: Number format, with thousands separators. `Console.WriteLine("{0:N}", 1234567);` will print `1,234,567.00`.
  * `{0:C}`: Currency format, based on your system's culture. `Console.WriteLine("{0:C}", 90);` will print `EGP 90.00` in Egypt.
  * `{0:P}`: Percentage format. `Console.WriteLine("{0:P}", 0.9);` will print `90.00%`.

-----

### 🕰️ 11. Dates and Times

The `DateTime` struct is used to represent a date and time. It's a powerful tool for handling time-related data.

  * `DateTime.Now`: Gets the current local date and time.
  * `.AddDays()`, `.AddYears()`: Methods to add or subtract from a `DateTime` object.
  * Custom Formatting: You can format a `DateTime` object using format specifiers like `yyyy` (year), `MMMM` (full month name), `dddd` (full day name), etc.

<!-- end list -->

```csharp
DateTime now = DateTime.Now;
Console.WriteLine($"Current date: {now:dddd, MMMM dd, yyyy}");

// Add 5 years to the current date
DateTime fiveYearsLater = now.AddYears(5);
Console.WriteLine($"In 5 years, it will be: {fiveYearsLater:yyyy-MM-dd}");
```

-----

### 🧑‍💻 12. Getting User Input

Your programs can interact with users by getting input from the console.

  * `Console.ReadLine()`: This method waits for the user to type something and press Enter. It always returns the input as a `string`. If you need a number, you must parse it.

<!-- end list -->

```csharp
Console.Write("Please enter your name: ");
string userName = Console.ReadLine();
Console.WriteLine($"Hello, {userName}!");

// Getting a number from the user
Console.Write("Enter your age: ");
// Since ReadLine() returns a string, we parse it to an integer.
int userAge = int.Parse(Console.ReadLine());
Console.WriteLine($"You are {userAge} years old.");
```

-----

### ✅ Summary Cheat Sheet

| Concept                 | Explanation & Example                                     |
| :---------------------- | :-------------------------------------------------------- |
| **Variable Declaration** | `int age = 25;` - Creates a container for a whole number. |
| **Printing to Console** | `Console.WriteLine("Hello!");` - Displays text.           |
| **Getting User Input** | `string name = Console.ReadLine();` - Reads text input.     |
| **String to Number** | `int.Parse("30")` - Converts a string to an integer.    |
| **Number to String** | `price.ToString()` - Converts a number to its string form. |
| **String Interpolation** | `$"Price is {price}"` - The best way to format strings. |
| **Date & Time** | `DateTime.Now`, `now.AddDays(7)` - Handles date operations.|
| **Number Formatting** | `"{0:C}", 100` - Formats as currency ($100.00).            |
| **Increment/Decrement** | `i++` (Postfix), `++i` (Prefix)                           |
