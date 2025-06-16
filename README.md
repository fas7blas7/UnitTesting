### 🗂️ Project Setup

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
📅 Commit Progress Update:

📅 Current Progress: 454 commits
📊 Progress Bar:
█████████████████████████████████████████████████░90.8% (454/500)

📌 Milestones:
✅ 100 commits
✅ 200 commits
✅ 300 commits
✅ 400 commits
🔲 500 commits (🎉)

🎯 Commit Progress Tracker
🚀 Goal: 500 commits in 2025
