
# Generate Integration test for the class

1. Open the Spring Boot project in Visual Studio Code.
2. Open `CalculatorController.java` file
3. Open Command Palette **(Ctrl + Shift + P)** then search for `Copilot: Generate Unit Test`.
4. You will see the copilot open new file and generate the unit test for `CalculatorController` class.

    > **Tips:** if you want to generate the unit test for specific method, you can select the method and use the command `Copilot: Generate Unit Test`.

5. You can use **ask copilot** to adjust the test unit or add more test cases. try following prompt:

```
add paremterized test
```

6. Finally, you should get something like this:

```java

package th.in.nextflow.NextflowBoot;

import static org.junit.jupiter.api.Assertions.assertEquals;
import static org.junit.jupiter.api.Assertions.assertThrows;
import org.junit.jupiter.api.BeforeEach;
import org.junit.jupiter.api.Test;
import org.junit.jupiter.api.AfterEach;


public class CalculatorTest {

    private Calculator calculator;

    @BeforeEach
    public void setUp() {
        calculator = new Calculator();
    }

    @Test
    public void testAddPositiveNumbers() {
        int result = calculator.add(3, 4);
        assertEquals(7, result, "3 + 4 should equal 7");
    }

    @Test
    public void testAddNegativeNumbers() {
        int result = calculator.add(-3, -4);
        assertEquals(-7, result, "-3 + -4 should equal -7");
    }

    @Test
    public void testAddPositiveAndNegativeNumbers() {
        int result = calculator.add(3, -4);
        assertEquals(-1, result, "3 + -4 should equal -1");
    }

    @Test
    public void testAddWithZero() {
        int result = calculator.add(3, 0);
        assertEquals(3, result, "3 + 0 should equal 3");
    }

    @Test
    public void testSubtractPositiveNumbers() {
        int result = calculator.subtract(4, 3);
        assertEquals(1, result, "4 - 3 should equal 1");
    }

    @Test
    public void testSubtractNegativeNumbers() {
        int result = calculator.subtract(-4, -3);
        assertEquals(-1, result, "-4 - -3 should equal -1");
    }

    @Test
    public void testSubtractPositiveAndNegativeNumbers() {
        int result = calculator.subtract(3, -4);
        assertEquals(7, result, "3 - -4 should equal 7");
    }

    @Test
    public void testSubtractWithZero() {
        int result = calculator.subtract(3, 0);
        assertEquals(3, result, "3 - 0 should equal 3");
    }

    @Test
    public void testMultiplyPositiveNumbers() {
        int result = calculator.multiply(3, 4);
        assertEquals(12, result, "3 * 4 should equal 12");
    }

    @Test
    public void testMultiplyNegativeNumbers() {
        int result = calculator.multiply(-3, -4);
        assertEquals(12, result, "-3 * -4 should equal 12");
    }

    @Test
    public void testMultiplyPositiveAndNegativeNumbers() {
        int result = calculator.multiply(3, -4);
        assertEquals(-12, result, "3 * -4 should equal -12");
    }

    @Test
    public void testMultiplyWithZero() {
        int result = calculator.multiply(3, 0);
        assertEquals(0, result, "3 * 0 should equal 0");
    }

    @Test
    public void testDividePositiveNumbers() {
        double result = calculator.divide(8, 4);
        assertEquals(2.0, result, "8 / 4 should equal 2.0");
    }

    @Test
    public void testDivideNegativeNumbers() {
        double result = calculator.divide(-8, -4);
        assertEquals(2.0, result, "-8 / -4 should equal 2.0");
    }

    @Test
    public void testDividePositiveAndNegativeNumbers() {
        double result = calculator.divide(8, -4);
        assertEquals(-2.0, result, "8 / -4 should equal -2.0");
    }

    @Test
    public void testDivideWithZeroNumerator() {
        double result = calculator.divide(0, 4);
        assertEquals(0.0, result, "0 / 4 should equal 0.0");
    }

    @Test
    public void testDivideByZero() {
        assertThrows(IllegalArgumentException.class, () -> {
            calculator.divide(8, 0);
        }, "Division by zero should throw IllegalArgumentException");
    }

    @Test
    public void testDivideByOne() {
        double result = calculator.divide(8, 1);
        assertEquals(8.0, result, "8 / 1 should equal 8.0");
    }

    @Test
    public void testDivideNegativeByPositive() {
        double result = calculator.divide(-8, 4);
        assertEquals(-2.0, result, "-8 / 4 should equal -2.0");
    }

    @Test
    public void testDividePositiveByNegative() {
        double result = calculator.divide(8, -4);
        assertEquals(-2.0, result, "8 / -4 should equal -2.0");
    }

    @AfterEach
    public void tearDown() {
        calculator = null;
    }
}
```

7. You can try to run test with following methods:
   1. Use Test Explorer in Visual Studio Code
   2. Ask Copilot Chat to suggest the run test command for you.