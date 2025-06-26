🗂️ Project Setup

🧾 **Solution File**:  
`UnitTestingMethods.sln` – Entry point for the entire solution, linking all projects.

📁 **Folder Structure**:
- `.vs/` – Visual Studio solution-specific config and metadata (auto-generated).
- `TestApp/` – The main application logic lives here. This contains the implementation classes like `Calculate`.
- `TestApp.UnitTests/` – Contains all unit tests. Uses **NUnit** for testing the main app logic in `TestApp`.

🧪 **Testing Framework**:  
This project uses [NUnit](https://nunit.org/) for writing and executing unit tests. Tests live in the `TestApp.UnitTests` project and follow the Arrange–Act–Assert pattern.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1️⃣ CalculateTests 🧪  
Namespace: TestApp.UnitTests  
📌 Description:  
Unit tests for a calculator-like class named `Calculate`.  
Currently tests:
- `Addition(a, b)` – checks if two numbers are added correctly  
- `Subtraction(a, b)` – checks if subtraction returns the correct result

🧪 Test Code:

```csharp
using NUnit.Framework;

namespace TestApp.UnitTests;

public class CalculateTests
{
    [Test]
    public void Test_Addition()
    {
        // Arrange
        Calculate calculator = new();

        // Act
        int actual = calculator.Addition(5, 2);

        // Assert
        Assert.AreEqual(7, actual, "Addition did not work properly.");
    }

    [Test]
    public void Test_Subtraction()
    {
        // Arrange
        Calculate calculator = new();
        int firstNum = 5;
        int secondNum = 2;
        int expected = 3;

        // Act
        int actual = calculator.Subtraction(firstNum, secondNum);

        // Assert
        Assert.AreEqual(expected, actual, "Subtraction did not work properly.");
    }
}

```
✅ 2️⃣ FactorialTests 🧪
Namespace: TestApp.UnitTests
📌 Description:
Unit tests for a method CalculateFactorial(int number) in a Factorial class.
Covers:

Factorial of 0 returns 1

Factorial of a positive number (e.g., 5) returns the correct result

🧪 Test Code:

```csharp
using NUnit.Framework;

namespace TestApp.UnitTests;

public class FactorialTests
{
    [Test]
    public void Test_CalculateFactorial_InputZero_ReturnsOne()
    {
        //Arrange
        int inputNumber = 0;
        int expected = 1;

        //Act
        int result = Factorial.CalculateFactorial(inputNumber);

        //Assert
        Assert.AreEqual(expected, result);
    }

    [Test]
    public void Test_CalculateFactorial_InputPositiveNumber_ReturnsCorrectFactorial()
    {
        //Arrange
        int inputNumber = 5;
        int expected = 120;

        //Act
        int result = Factorial.CalculateFactorial(inputNumber);

        //Assert
        Assert.AreEqual(expected, result);
    }
}

```
✅ 3️⃣ GradesTests 📝
Namespace: TestApp.UnitTests
📌 Description:
Unit tests for the GradeAsWords(double grade) method in the Grades class.
Covers both valid and invalid inputs:

Valid grades return their descriptive strings (e.g. "Good", "Excellent")

Edge cases (grades outside the valid 2.00–6.00 range) return "Invalid!"

🧪 Test Code:

```csharp

using NUnit.Framework;

namespace TestApp.UnitTests;

public class GradesTests
{
    [TestCase(2.60, "Fail")]
    [TestCase(3.80, "Good")]
    [TestCase(4.20, "Good")]
    [TestCase(4.90, "Very Good")]
    [TestCase(5.30, "Very Good")]
    [TestCase(5.60, "Excellent")]
    public void Test_GradeAsWords_ReturnsCorrectString(double grade, string expected)
    {
        // Act
        string actual = Grades.GradeAsWords(grade);

        // Assert
        Assert.AreEqual(expected, actual);
    }

    [TestCase(1.00, "Invalid!")]
    [TestCase(1.99, "Invalid!")]
    [TestCase(6.01, "Invalid!")]
    [TestCase(7.00, "Invalid!")]
    public void Test_GradeAsWords_ReturnsCorrectString_EdgeCases(double grade, string expected)
    {
        // Act
        string actual = Grades.GradeAsWords(grade);

        // Assert
        Assert.AreEqual(expected, actual);
    }
}

```
✅ 4️⃣ TriangleTests 🛆
Namespace: TestApp.UnitTests
📌 Description:
Unit tests for the PrintTriangle(int n) method in the Triangle class.
Covers:

Base case where size is 0 (empty result)

Size 3 – standard small triangle

Size 5 – symmetrical full triangle

🧪 Test Code:

```csharp

using NUnit.Framework;
using System;

namespace TestApp.UnitTests;

public class TriangleTests
{
    [Test]
    public void Test_Triangle_OutputMatchesExpected_Size0()
    {
        //Arrange
        int inputNumber = 0;

        //Act 
        string result = Triangle.PrintTriangle(inputNumber);

        //Assert
        Assert.IsEmpty(result);
    }

    [Test]
    public void Test_Triangle_OutputMatchesExpected_Size3()
    {
        //Arrange
        int inputNumber = 3;
        string expected =    $"1" +
        $"{Environment.NewLine}1 2" +
        $"{Environment.NewLine}1 2 3" +
        $"{Environment.NewLine}1 2" +
        $"{Environment.NewLine}1";

        //Act 
        string result = Triangle.PrintTriangle(inputNumber);

        //Assert
        Assert.That(result, Is.EqualTo(expected));
    }

    [Test]
    public void Test_Triangle_OutputMatchesExpected_Size5()
    {
        //Arrange
        int inputNumber = 5;
        string expected =    $"1" +
        $"{Environment.NewLine}1 2" +
        $"{Environment.NewLine}1 2 3" +
        $"{Environment.NewLine}1 2 3 4" +
        $"{Environment.NewLine}1 2 3 4 5" +
        $"{Environment.NewLine}1 2 3 4" +
        $"{Environment.NewLine}1 2 3" +
        $"{Environment.NewLine}1 2" +
        $"{Environment.NewLine}1";

        //Act 
        string result = Triangle.PrintTriangle(inputNumber);

        //Assert
        Assert.That(result, Is.EqualTo(expected));
    }
}
```
📅 Commit Progress Update:
📅 Current Progress: 460 commits
📊 Progress Bar:
█████████████████████████████████████████████████████ 92.0% (460/500)

📌 Milestones:
✅ 100 commits
✅ 200 commits
✅ 300 commits
✅ 400 commits
🔲 500 commits (🎉)
