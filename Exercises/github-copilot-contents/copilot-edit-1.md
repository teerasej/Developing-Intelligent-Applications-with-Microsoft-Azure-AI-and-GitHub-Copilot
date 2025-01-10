# Using Copilot Edits 

1. Open the project in Visual Studio Code.
2. If you have not done so, create a new file named `Calculator.cs` at the root of the project with the following code:

    ```csharp
    namespace Web
    {
        public class Calculator
        {
            public int Plus(int a, int b)
            {
                return a + b;
            }

            public int Multiply(int a, int b)
            {
                return a * b;
            }
        }
    }
    ```

3. Open the file `Calculator.cs`.
4. Open GitHub Copilot Chat, but use the `Copilot Edit` button to switch to Copilot Edit mode.
5. Notice that there is a **Working set** at the bottom of the chat window which includes the `Calculator.cs` file. You can add more files to the working set by clicking on the `+` button.
6. Prompt the following message to the chat:

    ```
    I want to add a divide feature to the calculator.
    ```
7. Copilot will generate the code for you at the place that it thinks is correct. You can review, accept, or reject the code.

## Summary

In this exercise, you have learned how to use Copilot Edit to generate code for the feature that you want to add to the existing codebase. This feature is useful when you want to add a new feature to the existing codebase.