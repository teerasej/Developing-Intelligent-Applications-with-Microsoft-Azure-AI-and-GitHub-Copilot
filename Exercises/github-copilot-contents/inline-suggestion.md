# Triggering inline suggestion (ghost text)

1. Open the project in Visual Studio Code.
2. Open the file `Index.cshtml.cs` in the `Pages` folder.
3. Below the `OnPostAsync` method, enter and try to type the following code:

    ```csharp
    public async Task<IActionResult> OnPostDeleteAsync()
    ```

4. GitHub Copilot will suggest the implementation based on the context of your project.
5. You can rotate through the suggestions by using the floating suggestion box.
6. You can press `Tab` to accept the suggestion.

