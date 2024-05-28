import java.util.Scanner;

public class Calculator {
    
    // Method to perform addition
    public static double add(double a, double b) {
        return a + b;
    }
    
    // Method to perform subtraction
    public static double subtract(double a, double b) {
        return a - b;
    }
    
    // Method to perform multiplication
    public static double multiply(double a, double b) {
        return a * b;
    }
    
    // Method to perform division
    public static double divide(double a, double b) {
        if (b == 0) {
            System.out.println("Error: Division by zero is not allowed.");
            return 0;
        }
        return a / b;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        double num1, num2;
        char operator;
        boolean continueCalculating = true;

        while (continueCalculating) {
            System.out.println("Enter first number: ");
            num1 = scanner.nextDouble();
            
            System.out.println("Enter an operator (+, -, *, /): ");
            operator = scanner.next().charAt(0);
            
            System.out.println("Enter second number: ");
            num2 = scanner.nextDouble();

            double result;
            switch (operator) {
                case '+':
                    result = add(num1, num2);
                    break;
                case '-':
                    result = subtract(num1, num2);
                    break;
                case '*':
                    result = multiply(num1, num2);
                    break;
                case '/':
                    result = divide(num1, num2);
                    break;
                default:
                    System.out.println("Invalid operator!");
                    continue;
            }
            
            System.out.println("The result is: " + result);

            System.out.println("Do you want to perform another calculation? (yes/no)");
            String response = scanner.next();
            if (response.equalsIgnoreCase("no")) {
                continueCalculating = false;
            }
        }
        
        scanner.close();
        System.out.println("Calculator is closed.");
    }
}
