### This file contains the main class of my Java Calculator 

Code Blockcode:
```java
import java.util.Scanner;

public class JavaCalculator {
	
    public static Scanner inputScanner = new Scanner(System.in); //Global scanner used to handle all inputs for the program
    
    /** Java Calculator print menu: 
	 * @author Luke Baker 
	 *date: October 22, 2018
	 *@return void - nothing.
	 *This method prints a menu so the user can see what inputs do which functions
	 */
    public static void printMenu() {
        System.out.println("Please choose what function to execute:");
        System.out.println("For addition press 1");
        System.out.println("For subtraction press 2");
        System.out.println("For multiplication press 3");
        System.out.println("For division press 4");
        System.out.println("For mudulo division press 5");
        System.out.println("To rase to a power press 6");
        System.out.println("To take a root press 7");
        System.out.println("To exit the program press 8");
    }
    /** Java Calculator Get Input Method 
	 * @author Luke Baker 
	 *date: October 22, 2018
	 *@return String - This program returns a string.
	 *This method takes input from the user and checks to make sure it is a valid input. It then returns this string to be processed later in the code. 
	 */
    public static String getInput() {
        String stringInput ="";
        while(true) {
            if (inputScanner.hasNextDouble() || inputScanner.hasNext("PI") || inputScanner.hasNext("pi") || inputScanner.hasNext("e") || inputScanner.hasNext("E")){
                stringInput = inputScanner.next();
                break;
            } else {
                inputScanner.next();
                System.out.println("Please enter valid inputs");
            }
        }
        return stringInput;
    }

    /** Java Calculator Choice Processor
	 * @author Luke Baker 
	 *date: October 22, 2018
	 *@return boolean - returns either true or false;
	 *This program take and integer. It first calls the getInput method to get user inputs, then instantiates a CalculatorInputs object with the given inputs. Finally, it processes the choice from the user and then selects the correct functions to call from Calculator Inputs.
	 *@param This program takes an integer input
	 */
    public static void processChoice (int i) {
        System.out.println("Please enter your first input");
        String inputOne = getInput();
        System.out.println("Please enter your second input");
        String inputTwo = getInput();
        CalculatorInputs functionCalculatorInputs = new CalculatorInputs(inputOne, inputTwo);
        if(i == 1) {
            System.out.printf("Your result is: %s\n",functionCalculatorInputs.addBothInputs());
        } else if (i == 2) {
            System.out.printf("Your result is: %s \n", functionCalculatorInputs.subtractBothInputs());
        } else if (i == 3) {
            System.out.printf("Your result is: %s \n", functionCalculatorInputs.multiplyInputs());
        } else if (i == 4) {
            System.out.printf("Your result is: %s \n", functionCalculatorInputs.divideInputs());
        } else if (i == 5) {
            System.out.printf("Your result is: %s \n", functionCalculatorInputs.moduloDivision());
        } else if (i == 6) {
            System.out.printf("Your result is: %s \n", functionCalculatorInputs.raiseToAPower());
        } else if (i == 7) {
            System.out.printf("Your result is: %s \n", functionCalculatorInputs.takeAnyRoot());
        }
    }
    
    /** Basic Java Calculator
	 * @author Luke Baker 
	 * @version 3.0.0
	 * main is the main method 
	 * Date: October 22, 2018
	 * @param args is an array of words passes in via the command line
	 * @return void - nothing
	 */
    public static void main(String[] args) {
       
        int menuSelection = 0; // variable to select which math function the user wants performed
        while(true){
            printMenu();//method call that prints the menu for the calculator
            while(true) { //code to get inputs form user, and assign the inputs to menu selection. Also acts as a gatekeeper ensure the user only give valid inputs
                if(inputScanner.hasNextInt()) {
                    menuSelection = inputScanner.nextInt();
                    if(menuSelection > 0 && menuSelection < 9) {
                        break;
                    } 
                } else {
                    inputScanner.next();
                }
                System.out.println("Please enter a value from the menu selection");
            }
            if(menuSelection == 8) { //code to make sure program progresses no further if the user selects the close option
                System.out.println("Thank you for using my program");
                break;
            }    
            processChoice(menuSelection); //method call to processChoice that will perform all the calculator functions.
        }
    }

}
```
