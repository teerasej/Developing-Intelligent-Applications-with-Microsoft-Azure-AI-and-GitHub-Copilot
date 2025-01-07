
# Comment to Code

## Exercise 1: Generate the code from the comment

1. Open the Spring Boot project in Visual Studio Code.
2. Open the file `CalculatorController.java` in the package `th.in.nextflow.NextflowBoot.controller`.
3. The current code should look like this:

    ```java
    package th.in.nextflow.NextflowBoot.controller;

    import org.springframework.web.bind.annotation.RestController;
    import org.springframework.web.bind.annotation.GetMapping;
    import org.springframework.web.bind.annotation.PostMapping;
    import org.springframework.web.bind.annotation.RequestBody;

    // The calculator controller will provide the RESTful API for the calculator
    // it contains the following methods:
    // - add
    // - subtract
    // - multiply
    // - divide
    // client can send a post request with json body to the corresponding endpoint to get the result
    @RestController
    public class CalculatorController {

        // This url to check that the server is running
        @GetMapping("/ping")
        public String ping() {
            return "pong";
        }

    }
    ```

4. Below the `ping()` method, try to use commenting with context to generate the code for the `add()` method. Try to craft the comment that: 
   
    ```
    - method handle get request '/add'.
    - this method takes two numbers.
    - return the sum of the two numbers.
    - the request should be in the form of '/add?a=1&b=2'.
    - make the result response in the form of json: { "result": 3 }
    ```

5. After you have the comment, You should make it work similar to the following code:

    ```java
        // a get request method '/add' that takes two numbers and return the sum of them
        // the request should be in the form of '/add?a=1&b=2'
        // make the result response in the form of json: 
        // { "result": 3 }
        @GetMapping("/add")
        public String add(@RequestParam int a, @RequestParam int b) {
            return "{ \"result\": " + (a + b) + " }";
        }
    ```

6. Use command below to start the Spring Boot application:

    ```bash
    ./mvnw spring-boot:run
    ```

7. Open the browser and navigate to `http://localhost:8080/add?a=1&b=2` and you should see the result `{"result": 3}`.

## Exercise 2: Modify the route

1. Select the code block:

```java
// a get request method '/add' that takes two numbers and return the sum of them
    // the request should be in the form of '/add?a=1&b=2'
    // make the result response in the form of json: 
    // { "result": 3 }
    @GetMapping("/add")
    public String add(@RequestParam int a, @RequestParam int b) {
        return "{ \"result\": " + (a + b) + " }";
    }
```

2. Use one of following method:
   1. `Ctrl + I` to open the inline copilot chat.
   2. Click on **Code Action** icon on the left side of the code block. then select **Modify with Copilot**
3. Try to use prompt to modify the code to handle the POST request with input data as JSON instead. The prompt should be like this:

    ```
    make this method accept POST request instead with json object as input data
    ```

4. After you have the code, you should have the following code:

    ```java
    // a post request method '/add' that takes two numbers in a json object and returns the sum of them
    // the request should be in the form of a json object: { "a": 1, "b": 2 }
    // make the result response in the form of json: 
    // { "result": 3 }
    @PostMapping("/add")
    public Map<String, Integer> add(@RequestBody Map<String, Integer> payload) {
        int a = payload.get("a");
        int b = payload.get("b");
        int result = a + b;
        Map<String, Integer> response = new HashMap<>();
        response.put("result", result);
        return response;
    }
    ```