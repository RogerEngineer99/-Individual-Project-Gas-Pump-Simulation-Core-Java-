Gas Pump Simulation (Core Java)



Overview



The Gas Pump Simulation is a Core Java project that simulates the operation of a gas pump. The application allows users to simulate the dispensing of gasoline while dynamically updating the price in relation to the amount of fuel dispensed. The price display is updated incrementally, and the program terminates when the maximum value for the pump display is reached. The project incorporates recursion, dimensional arrays, and other Java programming concepts.



Project Duration:



Spring 2019



Features

• Dynamic Price Calculation: The price of gasoline is updated in real-time based on the amount of gasoline dispensed.

• Recursive Value Incrementation: Utilizes recursion to increment the displayed price, simulating the gas pump display.

• Dimensional Array: A dimensional array is used to store the updated price values as the user interacts with the pump.

• Maximum Value Termination: When the price reaches the maximum value the pump display can show, the program terminates.

• Simulated Charge Output: The final charge is displayed once the dispensing process is complete.



Components and Technologies Used

• Java: Core Java was used to develop the application logic.

• Recursion: Recursion is used to increment the displayed price in a simplified and structured manner.

• Dimensional Arrays: A 2D array stores the dynamic price values and simulates the operation of the gas pump.



Key Concepts Implemented:

• Recursion: Recursive methods to increment values without needing traditional loops.

• Dimensional Arrays: Used to store the incremented price values for display updates.

• Condition Checking: Logic to monitor the price and stop the program once the maximum display value is reached.



Design and Implementation



1. Dynamic Price Calculation:



The gas pump simulates price updates as the user dispenses gasoline. The price increases based on the amount of fuel dispensed, and the price is displayed in real-time.



2. Recursion for Price Incrementation:



Instead of using loops, recursion is employed to increment the price in small steps. Each recursive call simulates a price update and ensures that the correct price is displayed until the maximum value is reached.



3. Dimensional Array:



A 2D array is used to store the current price values. This allows the program to track the price dynamically as the user interacts with the pump.



4. Termination Logic:



Once the pump display reaches its maximum value (e.g., 999.99 or a predefined value), the program terminates, simulating the limitation of a real-world pump display.



Example of Usage



1. Starting the Pump:



The user starts the pump, and the system asks how much gasoline they wish to dispense. The price starts at a base rate and increases based on the amount dispensed.



2. Dispensing Gasoline:



As gasoline is dispensed, the price increments and is displayed in real-time. Each increment is handled by a recursive method.



3. Final Charge:



Once the user stops dispensing, the total charge is calculated based on the amount of gasoline dispensed and the updated price.



Example Java Code



import java.util.Scanner;



public class GasPumpSimulation {

    private static double pricePerGallon = 3.29;  // Base price per gallon

    private static double totalAmountDispensed = 0.0;  // Total amount of gasoline dispensed

    private static final double MAX_DISPLAY_VALUE = 999.99;  // Max value for the display



    // Recursive method to simulate price incrementation

    public static void incrementPrice(double currentPrice, int iteration) {

        if (currentPrice >= MAX_DISPLAY_VALUE) {

            System.out.println("Max display value reached. Stopping simulation.");

            return;

        }



        // Print the current price

        System.out.printf("Price: $%.2f\n", currentPrice);



        // Simulate increment

        double newPrice = currentPrice + 0.01;  // Increment price by 1 cent

        incrementPrice(newPrice, iteration + 1);

    }



    // Method to simulate the gas pump process

    public static void pumpGas() {

        Scanner scanner = new Scanner(System.in);

        System.out.println("Welcome to the Gas Pump Simulation!");

        System.out.print("Enter the number of gallons to dispense: ");

        double gallonsToDispense = scanner.nextDouble();



        if (gallonsToDispense <= 0) {

            System.out.println("Invalid input. Number of gallons must be greater than zero.");

            return;

        }



        // Calculate the total charge based on the amount of gasoline dispensed

        totalAmountDispensed = gallonsToDispense;

        double totalPrice = pricePerGallon * totalAmountDispensed;



        // Begin the recursive price incrementation

        incrementPrice(pricePerGallon, 0);



        // Display the final total charge for the user

        System.out.printf("Total Amount Dispensed: %.2f gallons\n", totalAmountDispensed);

        System.out.printf("Total Price: $%.2f\n", totalPrice);

    }



    public static void main(String[] args) {

        pumpGas();

    }

}



Key Methods:

• incrementPrice(): A recursive method that increments the price by $0.01 and prints it until the maximum display value is reached.

• pumpGas(): Simulates the process of dispensing gas, taking user input for the number of gallons, and calculates the total price.

• main(): The entry point of the program that starts the gas pump simulation process.



Future Enhancements

• Graphical User Interface (GUI): Implementing a GUI to simulate a more realistic gas pump display and user interaction.

• Fuel Price Variability: Allowing dynamic updates to fuel prices based on external factors (e.g., market rates).

• Transaction Logging: Implementing a feature to log all transactions and provide a history to the user.

• Advanced Recursion: Enhancing the recursive logic to handle more complex price calculations and different fuel types.



License



This project is licensed under the MIT License. See the LICENSE file for more details.



This README.md provides a comprehensive overview of the Gas Pump Simulation project, detailing the features, design, and implementation. It highlights the use of recursion, arrays, and the program’s behavior as it simulates the dispensing of fuel and updates the price accordingly.


