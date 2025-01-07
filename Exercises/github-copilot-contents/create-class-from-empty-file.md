
# Create a class from empty file

1. Open the Spring Boot project in Visual Studio Code.
2. Create **an empty file** in package `th.in.nextflow.NextflowBoot`.
3. Name it `Calculator.java`
4. In the empty file, click on copilot suggestion on the top of empty file (or use Ctrl + I)
5. Use prompt the generate calculator class:

```
Create calculator class
```

6. filnally, you should get something like this:

```java
package th.in.nextflow.NextflowBoot;

public class Calculator {

    public int add(int a, int b) {
        return a + b;
    }

    public int subtract(int a, int b) {
        return a - b;
    }

    public int multiply(int a, int b) {
        return a * b;
    }

    public double divide(int a, int b) {
        if (b == 0) {
            throw new IllegalArgumentException("Division by zero is not allowed.");
        }
        return (double) a / b;
    }
}
```