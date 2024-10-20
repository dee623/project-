# project-simple calculator
import java.util.Scanner;

public class Calculator {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        boolean continueCalculating = true;

        while (continueCalculating) {
            System.out.println("Enter first number:");
            double num1 = scanner.nextDouble();

            System.out.println("Enter second number:");
            double num2 = scanner.nextDouble();

            System.out.println("Choose an operation: +, -, *, /");
            char operation = scanner.next().charAt(0);

            double result = 0;
            switch (operation) {
                case '+':
                    result = num1 + num2;
                    break;
                case '-':
                    result = num1 - num2;
                    break;
                case '*':
                    result = num1 * num2;
                    break;
                case '/':
                    if (num2 != 0) {
                        result = num1 / num2;
                    } else {
                        System.out.println("Error: Division by zero is not allowed.");
                        continue;
                    }
                    break;
                default:
                    System.out.println("Error: Invalid operation.");
                    continue;
            }

            System.out.printf("Result: %.2f%n", result);

            System.out.println("Do you want to perform another calculation? (yes/no)");
            String response = scanner.next();
            continueCalculating = response.equalsIgnoreCase("yes");
        }

        System.out.println("Calculator closed.");
        scanner.close();
    }
}
