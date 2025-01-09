
# Explore your workspace

## 1. Understanding the project

1. Select the copilot's icon on the top-center of the Visual Studio Code's windows
2. Type `@workspace` you will see the list of prompts that you can use to explore your workspace.
3. Add the following prompt to look like this:

    ```
    @workspace explain what is this probject
    ```

4. Press `Enter` to see the result.
5. Try with other prompts such as `@workspace show me the files in this project` or `@workspace show me the folders in this project` to see the result.

## 2. Understanding the code

1. Use the `new chat` button on the top of Copilot chat window
2. Open the `Program.cs` file.
3. Notice that the file's name appear in the chat window.
4. prompt the copilot with the following message:

    ```
    Explain the code in Program.cs
    ```

5. Press `Enter` to see the result.

## 3. Add file to ask more about the code

1. Use the `new chat` button on the top of Copilot chat window
2. While we open the `Program.cs` file, open the `Options.cs` file.
3. Back to the copilot chat window
4. Select `Attach context` button on the bottom of the chat window
5. Select the `Options.cs` file, you will see the file's name appear in the chat window.
6. Prompt the copilot with the following message:

    ```
    Explain the relation betweee these files
    ```
7. Press `Enter` to see the result.

## 4. Understand about codebase

1. Use the `new chat` button on the top of Copilot chat window
2. Use **hide** button in the chat window to hide the opening file as context.
3. Select `Attach context` button on the bottom of the chat window, and select the `Codebase` option.
4. Prompt the copilot with the following message:

    ```
    tell me how to connect a web api
    ```

5. Press `Enter` to see the result.

## 5. Comparing `#codebase` with the `#workspace`

1. Use the `new chat` button on the top of Copilot chat window
2. Use **hide** button in the chat window to hide the opening file as context.
3. Prompt the copilot with the following message:

    ```
    @workspace tell me how to connect a web api
    ```

4. Press `Enter` to see the result.
5. Compare the result with the previous one.

## 6. Checking anything 

1. Try to ask anything that you want to know about the codebase or workspace.
2. For example: 

```
@workspace Is there some thing can cause error when I run this project?
```

3. If you are looking for the ApiUrl use the following URL:

```
https://imgapi-nextflow-eyh5a5fmgmavd9as.eastus-01.azurewebsites.net/
```

## Summary

In this exercise, you have learned how to explore your workspace and understand the codebase with Github Copilot. You can use the `@workspace` and `@codebase` to explore the workspace and codebase respectively. You can also use the `Explain the code` prompt to understand the code in the file that you are currently opening. You can also use the `Attach context` to attach the context of the file that you are currently opening to the chat window. This will help Copilot to understand the context of the code that you are asking about.