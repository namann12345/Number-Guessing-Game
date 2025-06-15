package examination_system;
import java.util.Random;
import java.util.Scanner;
public class NumberGuessingGame {
	 public static void main(String[] args) {
	        Scanner scanner = new Scanner(System.in);
	        Random random = new Random();
	        boolean playAgain = true;

	        System.out.println("Welcome to the Number Guessing Game!");
	        System.out.println("------------------------------------");

	        while (playAgain) {
	            int targetNumber = random.nextInt(100) + 1;
	            int attempts = 0;
	            int maxAttempts = 10; 
	            boolean hasWon = false;

	            System.out.println("I have selected a number between 1 and 100.");
	            System.out.println("You have " + maxAttempts + " attempts to guess it!");

	          
	            while (attempts < maxAttempts) {
	                System.out.print("Enter your guess: ");
	                int userGuess = scanner.nextInt();
	                attempts++;

	                if (userGuess == targetNumber) {
	                    System.out.println("Congratulations! You guessed the number in " + attempts + " attempts!");
	                    hasWon = true;
	                    break;
	                } else if (userGuess < targetNumber) {
	                    System.out.println("Too low! Try again.");
	                } else {
	                    System.out.println("Too high! Try again.");
	                }

	                System.out.println("Attempts remaining: " + (maxAttempts - attempts));
	            }

	            if (!hasWon) {
	                System.out.println("Sorry, you've run out of attempts! The correct number was: " + targetNumber);
	            }

	 
	            System.out.print("Do you want to play again? (yes/no): ");
	            String response = scanner.next();
	            playAgain = response.equalsIgnoreCase("yes");
	        }

	        System.out.println("Thank you for playing the Number Guessing Game! Goodbye!");
	    }
	}



