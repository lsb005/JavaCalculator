## This file contains the Calculator Inputs Class that I used to build Calculator Input objects from

```java
import java.lang.Math;
public class CalculatorInputs {
	
    protected String firstInput;
    protected String secondInput;
    protected double convertedInputOne;
    protected double convertedInputTwo;
    
    /**Java Calculator Inputs Constructor Method
     * @author Luke Baker. 
     * Date: October 22, 2018 
     * @param firstInput : A String that is either pi or a string that can be converted to a double
     * @param secondInput: A String that is either pi or a string that can be converted to a double
     * @return CalculatorInputs object
     */
    public CalculatorInputs(String firstInput, String secondInput) {
        this.firstInput = firstInput;
        this.secondInput = secondInput;
        
        if (this.firstInput.matches("PI") || this.firstInput.matches("pi")) {
            this.convertedInputOne = Math.PI;
        } else if(this.firstInput.matches("e")|| this.firstInput.matches("E")) {
        	this.convertedInputOne = Math.E;
        } else {
            this.convertedInputOne = Double.parseDouble(firstInput);
        }
        
        if (this.secondInput.matches("PI") || this.secondInput.matches("pi")) {
            this.convertedInputTwo = Math.PI;
        } else if(this.secondInput.matches("E")|| this.secondInput.matches("e")) {
        	this.convertedInputTwo = Math.E;
        } else {
            this.convertedInputTwo = Double.parseDouble(secondInput);
        }
    }
    /**Calculator Inputs Get method for firstInput
     * @author Luke Baker. 
     * Date: October 22, 2018 
     * @return String: This method returns the string firstInput
     */
    public String getFirstInput() {
        return this.firstInput;
    }
    /**Calculator Inputs Set method for firstInput
     * @author Luke Baker. 
     * Date: October 22, 2018 
     * @param firstInput : A String that is either pi or a string that can be converted to a double
     * @return void
     */
    public void setFirstInput(String firstInput){
        this.firstInput = firstInput;
    }
    /**Calculator Inputs get method for secondInput
     * @author Luke Baker. 
     * Date: October 22, 2018 
     * @return String secondInput
     */
    public String getSecondInput() {
        return this.secondInput;
    }
    /**Calculator Inputs Set method for secondInput
     * @author Luke Baker. 
     * Date: October 22, 2018 
     * @param SecondInput : A String that is either pi or a string that can be converted to a double
     * @return void This method sets the value of secondInput.
     */
    public void setSecondInput(String secondInput) {
        this.secondInput = secondInput;
    }
    /**Calculator Inputs Get method for convertedInputOne
     * @author Luke Baker. 
     * Date: October 22, 2018 
     * @return String: This method returns the string convertedInputOne
     */
    public double getConvertedInputOne() {
        return this.convertedInputOne;
    }
    /**Calculator Inputs Set method for convertedInputOne
     * @author Luke Baker. 
     * Date: October 22, 2018 
     * @param convertedInputOne:A String that is either pi or a string that can be converted to a double
     * @return void This method sets the value of firstConvertedInput.
     */
    public void setFirstConvertedInput(double convertedInputOne){
        this.convertedInputOne = convertedInputOne;
    }
    /**Calculator Inputs Get method for convertedInputTwo
     * @author Luke Baker. 
     * Date: October 22, 2018 
     * @return String: This method returns the string convertedInputTwo
     */
    public double getSecondConvertedInput() {
        return this.convertedInputTwo;
    }
    /**Calculator Inputs Set method for convertedInputTwo
     * @author Luke Baker. 
     * Date: October 22, 2018 
     * @param convertedInputTwo : A String that is either pi or a string that can be converted to a double
     * @return void This method sets the value of secondInput.
     */
    public void setSecondConvertedInput(double convertedInputTwo) {
        this.convertedInputTwo = convertedInputTwo;
    }
    /**CalculatorInputs addBothInputs method
     * @author Luke Baker
     * Date: October 22, 2018
     * @return Double calculated by adding convertedInputOne and convertedInputTwo
     */
    public double addBothInputs() {
        return this.convertedInputOne + this.convertedInputTwo;
    }
    /**CalculatorInputs subtractBothInputs method
     * @author Luke Baker
     * Date: October 22, 2018
     * @return Double calculated by subtract convertedInputOne and convertedInputTwo
     */
    public double subtractBothInputs() {
        return this.convertedInputOne - this.convertedInputTwo;
    }
    /**CalculatorInputs multiplyInputs method
     * @author Luke Baker
     * Date: October 22, 2018
     * @return Double calculated by multiplying convertedInputOne and convertedInputTwo
     */
    public double multiplyInputs() {
        return this.convertedInputOne * this.convertedInputTwo;
    }
    /**CalculatorInputs divideInputs method
     * @author Luke Baker
     * Date: October 22, 2018
     * @return Double calculated by dividing convertedInputOne and convertedInputTwo
     */
    public double divideInputs() {
    	double i = 0;
    	try {
    		if(convertedInputTwo == 0) {
    			throw new ArithmeticException();
    		} else {
    			i = convertedInputOne / this.convertedInputTwo;
    		}
    	} catch (ArithmeticException e) {
    		System.out.println("You should not divide by 0");
    	}
    	return i;
    }
    /**CalculatorInputs moduloDivision method
     * @author Luke Baker
     * Date: October 22, 2018
     * @return Double calculated by using modulo division for the doubles convertedInputOne and convertedInputTwo
     */
    public double moduloDivision() {
    	double i = 0;
    	try {
    		if(convertedInputTwo == 0) {
    			throw new ArithmeticException();
    		} else {
    			i = convertedInputOne % this.convertedInputTwo;
    		}
    	} catch (ArithmeticException e) {
    		System.out.println("You should not divide by 0");
    	}
    	return i;
    }
    /**CalculatorInputs raiseToAPower method
     * @author Luke Baker
     * Date: October 22, 2018
     * @return Double calculated by using convertedInputTwo as an exponent for convertedInputOne
     */
    public double raiseToAPower() {
        return Math.pow(convertedInputOne, convertedInputTwo);
    }
    /**CalculatorInputs takeAnyRoot method
     * @author Luke Baker
     * Date: October 22, 2018
     * @return Double calculated by using 1/convertedInputTwo as an exponent for convertedInputOne
     */
    public double takeAnyRoot() {
    	if(convertedInputTwo == 0) {
    		return 1;
    	}else {
            return Math.pow(convertedInputOne, 1/convertedInputTwo);

    	}
    }
}
```
