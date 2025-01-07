
# Triggering inline suggestion

1. Open the Spring Boot project in Visual Studio Code.
2. Create new package `th.in.nextflow.NextflowBoot.controller`
3. Create new file `CalculatorController.java` in this package.
4. You will get a template of the class with the following content:

    ```java
    package th.in.nextflow.NextflowBoot.controller;

    // The calculator controller will provide the RESTful API for the calculator
    // it contains the following methods:
    // - add
    // - subtract
    // - multiply
    // - divide
    // client can send a post request with json body to the corresponding endpoint to get the result
    public class CalculatorController {
        
    }
    ```

5. Add the following comment code to the file, this will be use as a hint for the copilot to generate the code:

    ```java
    package th.in.nextflow.NextflowBoot.controller;

    // The calculator controller will provide the RESTful API for the calculator
    // it contains the following methods:
    // - add
    // - subtract
    // - multiply
    // - divide
    // client can send a post request with json body to the corresponding endpoint to get the result
    public class CalculatorController {
        
    }
    ```

6. This time, you will assign `@RestController` annotation to the class. 

    ```java
    package th.in.nextflow.NextflowBoot.controller;

    import org.springframework.web.bind.annotation.RestController;

    // The calculator controller will provide the RESTful API for the calculator
    // it contains the following methods:
    // - add
    // - subtract
    // - multiply
    // - divide
    // client can send a post request with json body to the corresponding endpoint to get the result
    @RestController
    public class CalculatorController {
        
    }
    ```

7. Now, you will use **Comment to code technique** to generate the code for use to check the server is running. Add the following comment code to the file:

    ```java
    package th.in.nextflow.NextflowBoot.controller;

    import org.springframework.web.bind.annotation.RestController;

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

    }
    ```
8. After enter new line, you should see the suggestion. Adjust it if you want with selecting code and select **Modify with Copilot** in Code Action.
9. The code for next step should be like this: 

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

9. Try to add a simple addition method into the class like below


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

    @PostMapping("/add")
    public int add(@RequestBody AddRequest request) {
        return request.getA() + request.getB();
    }

    static class AddRequest {
        private int a;
        private int b;

        public int getA() {
            return a;
        }

        public void setA(int a) {
            this.a = a;
        }

        public int getB() {
            return b;
        }

        public void setB(int b) {
            this.b = b;
        }
    }
}
```