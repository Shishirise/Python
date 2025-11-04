//Import the necessary package
import java.util.*;

//Declare public class 
//Public static to accepts an array of String arguments

public class Quadraticequations {
    public static void main(String[] args) {
        
        // Scanner object to accepts the user input
         Scanner in = new Scanner(System.in);
        
        //Print necessary header
        System.out.println("Shishir Adhikari");
        System.out.println("CMPS-4143");
		System.out.println("In this program we will find both solutions of quadratic equations using formula.\n");
		
		 //Using while loop due to condition like a is always greater than 0 and allow to quit
        //Print the statement where user enters the value for coefficients
         while(true){
            System.out.println("Enter the coefficients a b c (enter 0 0 0 to quit):");
            
            // Declare variable  a,b,c and read value from user input
            double a = in.nextDouble();  
            double b = in.nextDouble();
            double c = in.nextDouble();  
            
            // Using if statement for qutting the program( if a,b,c= 0,0,0)
             if( a == 0 && b == 0 && c == 0){
                System.out.println("Program quit.");
                break; //Exit the loop and quit program
            }
            
            // Using if statement to ensure that a is always greater than 0 (if a>0)
            if(a == 0){
                System.out.println("Coefficient a should be greater than 0.");
                continue; //Ask the user for input again
            }
            
            //Declare discriminant and calculate its value using the formula
            //Declare two output of the equations
            double discriminant = b*b - 4*a*c;
            double x1, x2;

           // Use if statement to check if the discriminant is less than 0
           // Else, calculate the both real solutions
           if(discriminant < 0){
                System.out.println("There are no real solutions for this equation.");
            } else {
                x1 = (-b + Math.sqrt(discriminant)) / (2*a);
                x2 = (-b - Math.sqrt(discriminant)) / (2*a);
                
                // Check if two solutions are same,print only one
                //Print both soultions
                if(x1 == x2){
                    System.out.printf("x=%.2f\n", x1); // Call variables x1 or x2 
                } else {
                    System.out.printf("x=%.2f or x=%.2f\n", x1, x2); // Call variables x1 and x2 
                }
            }
        }
    }
}

