# Inline chat

## 1. Create a calculator class

1. Open the project in Visual Studio Code.
2. Create an empty file named `Calculator.cs` at the root of the project.
3. Open the file `Calculator.cs`.
4. Use **Ctrl + I** to trigger the inline chat.
5. Prompt the following message to the chat:
   ```
   Create a calculator class that has plus and multiply methods.
   ```
6. Copilot will generate the code for you. The code should look like this:
   ```csharp
    namespace CalculatorApp
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

7. If you notice that the code is not generated as expected, you can ask Copilot to generate the code again by typing the message:
   ```
   correct the namespace #codebase
   ```

8. Apply prompts to adjust the code as needed.
9. Select `Accept` to apply the code to the file.

## 2. Implement the minus method

1. Move the cursor to the end of the `Multiply` method.
2. Use **Ctrl + I** to trigger the inline chat.
3. Prompt the following message to the chat:
   ```
   Add one more necessary method.
   ```
4. Copilot will generate the code for you. The code should look like this:
   ```
    public int Minus(int a, int b)
    {
        return a - b;
    }
   ```
5. Apply prompts to adjust the code as needed.
6. Select `Accept` to apply the code to the file.