🎓 C# Beginner Guide
Simple English | Clean Examples | Easy Learning

🧠 1. What Are Variables?
Variables are containers to store data like numbers, names, prices, etc.

🔹 Common Data Types:
Data Type	Example	Use For
int	25	Whole numbers
float	3.5F	Small decimal numbers
double	15.99	Decimal numbers (default)
decimal	99.99M	Money or high-precision values
string	"Ali"	Text
char	'A'	Single character
bool	true / false	Yes/No, On/Off decisions
📝 2. Declaring and Using Variables
int age = 25;
string name = "Ali";
float temperature = 36.6F;
bool isOnline = true;

Console.WriteLine("Name: " + name);
Console.WriteLine("Age: " + age);
💬 3. Writing Output
Console.WriteLine() - prints and moves to next line
Console.Write() - prints and stays on the same line
Console.Write("Hello ");
Console.WriteLine("World!");
💡 Shortcut in Visual Studio: Type cw + Tab + Tab = Console.WriteLine();

🧮 4. Math Operations
int a = 10;
int b = 3;

int sum = a + b;       // 13
int diff = a - b;      // 7
int product = a * b;   // 30
double division = (double)a / b; // 3.33

Console.WriteLine("Sum: " + sum);
🔀 5. Prefix vs Postfix Increment
int i = 5;

Console.WriteLine(i);     // 5
Console.WriteLine(i++);   // 5 (then becomes 6)
Console.WriteLine(i);     // 6

int j = 5;
Console.WriteLine(++j);   // 6 (increased before printing)
🔁 6. Type Conversion
✅ Implicit (small → big, automatic)
int x = 10;
double y = x;  // OK
❌ Explicit (big → small, needs casting)
double d = 12.9;
int i = (int)d;  // Loses decimals → 12
🔍 Check the Type
int number = 100;
Console.WriteLine(number.GetType());  // Output: System.Int32
🔄 7. Converting Strings and Numbers
string → int
string age = "30";
int ageValue = int.Parse(age);
int → string
int price = 150;
string text = price.ToString();
✨ 8. var Keyword (Auto Type Detection)
var city = "Cairo";     // string
var number = 100;       // int
var isActive = true;    // bool
🧵 9. String Formatting
🔹 Using string.Format()
string name = "Sara";
int score = 90;

string msg = string.Format("{0} scored {1} points", name, score);
Console.WriteLine(msg);
🔹 String Interpolation (Better Way)
Console.WriteLine($"{name} scored {score} points");
🧱 10. Using StringBuilder
using System.Text;

var sb = new StringBuilder();
sb.Append("Hello");
sb.AppendLine(" World!");
sb.AppendFormat("You have {0} new messages.", 3);

Console.WriteLine(sb.ToString());
📊 11. Formatting Numbers
Console.WriteLine("Number: {0:N}", 90);      // 90.00
Console.WriteLine("Money: {0:C}", 90);       // $90.00 (or local currency)
Console.WriteLine("Percent: {0:P}", 0.9);    // 90.00%
Console.WriteLine("Padded: {0:D5}", 12);     // 00012
Console.WriteLine("Hex: {0:X}", 255);        // FF
🕰️ 12. Dates and Time
🔹 Current Date and Time
DateTime now = DateTime.Now;
Console.WriteLine(now);
🔹 Custom Date
DateTime birthday = new DateTime(2000, 5, 20);
Console.WriteLine($"Birthday: {birthday:dddd, MMMM dd yyyy}");
// Output: Saturday, May 20 2000
🔹 Format Examples
Console.WriteLine($"Year: {now:yyyy}");
Console.WriteLine($"Month: {now:MMMM}");
Console.WriteLine($"Time: {now:HH:mm tt}");
🔹 Add Years or Days
var future = birthday.AddYears(5);
Console.WriteLine($"5 years later: {future:yyyy}");
📅 New Types in C# 10+
DateOnly & TimeOnly (if your version supports them)
DateOnly date = new DateOnly(2025, 8, 9);
TimeOnly startTime = new TimeOnly(8, 0);
TimeOnly endTime = new TimeOnly(17, 0);

TimeSpan duration = endTime - startTime;
Console.WriteLine($"Working Hours: {duration.TotalHours}");
🧑‍💻 13. Getting User Input
Console.Write("What is your name? ");
string name = Console.ReadLine();
Console.WriteLine($"Welcome, {name}!");
🎯 Input Example with Numbers
Console.Write("Enter your age: ");
int age = int.Parse(Console.ReadLine());

Console.Write("Enter your salary: ");
decimal salary = decimal.Parse(Console.ReadLine());

Console.WriteLine($"You are {age} years old and earn {salary:C}");
🎯 14. Mini Challenges
1️⃣ Day of Your Birthday
Console.Write("Enter your birthday (yyyy-mm-dd): ");
DateTime birthday = DateTime.Parse(Console.ReadLine());
Console.WriteLine($"You were born on a {birthday.DayOfWeek}");
2️⃣ Display Birthday in Full Format
Console.WriteLine($"Your birthday: {birthday:dddd 'of' MMMM yyyy}");
✅ Summary Cheat Sheet
Concept	Example
Declare variable	int x = 10;
Output	Console.WriteLine("Hi");
Input	string name = Console.ReadLine();
Convert to number	int.Parse("30")
Convert to string	price.ToString()
Format string	$"Price is {price}"
Dates	DateTime.Now, .AddYears()
StringBuilder	sb.Append("Hi")
Number formatting	{0:N}, {0:C}, {0:P}
