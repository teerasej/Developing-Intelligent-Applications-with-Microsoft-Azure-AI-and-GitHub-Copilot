# Explore your workspace

## 1. Understanding the project

1. Select the Copilot icon at the top-center of the Visual Studio Code window.
2. Type `@workspace` and you will see a list of prompts that you can use to explore your workspace.
3. Add the following prompt to look like this:

    ```
    @workspace explain what is this project
    ```

4. Press `Enter` to see the result.
5. Try other prompts such as `@workspace show me the files in this project` or `@workspace show me the folders in this project` to see the result.

## 2. Understanding the code

1. Use the `new chat` button at the top of the Copilot chat window.
2. Open the `Program.cs` file.
3. Notice that the file's name appears in the chat window.
4. Prompt Copilot with the following message:

    ```
    Explain the code in Program.cs
    ```

5. Press `Enter` to see the result.

## 3. Add file to ask more about the code

1. Use the `new chat` button at the top of the Copilot chat window.
2. While the `Program.cs` file is open, open the `Options.cs` file.
3. Go back to the Copilot chat window.
4. Select the `Attach context` button at the bottom of the chat window.
5. Select the `Options.cs` file, and you will see the file's name appear in the chat window.
6. Prompt Copilot with the following message:

    ```
    Explain the relation between these files
    ```
7. Press `Enter` to see the result.

## 4. Understand the codebase

1. Use the `new chat` button at the top of the Copilot chat window.
2. Use the **hide** button in the chat window to hide the open file as context.
3. Select the `Attach context` button at the bottom of the chat window, and select the `Codebase` option.
4. Prompt Copilot with the following message:

    ```
    Tell me how to connect a web API
    ```

5. Press `Enter` to see the result.

## 5. Comparing `#codebase` with the `#workspace`

1. Use the `new chat` button at the top of the Copilot chat window.
2. Use the **hide** button in the chat window to hide the open file as context.
3. Prompt Copilot with the following message:

    ```
    @workspace tell me how to connect a web API
    ```

4. Press `Enter` to see the result.
5. Compare the result with the previous one.

## 6. Checking for anything

1. Try to ask anything that you want to know about the codebase or workspace.
2. For example:

    ```
    @workspace Is there something that can cause an error when I run this project?
    ```

3. If you are looking for the ApiUrl, use the following URL:

```
https://imgapi-nextflow-eyh5a5fmgmavd9as.eastus-01.azurewebsites.net/
```

## Summary

In this exercise, you have learned how to explore your workspace and understand the codebase with GitHub Copilot. You can use the `@workspace` and `@codebase` prompts to explore the workspace and codebase respectively. You can also use the `Explain the code` prompt to understand the code in the file that you are currently opening. Additionally, you can use the `Attach context` button to attach the context of the file that you are currently opening to the chat window. This will help Copilot to understand the context of the code that you are asking about.