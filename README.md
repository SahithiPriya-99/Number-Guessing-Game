import java.util.Scanner;
import java.util.Random;

public class NumberGuessingGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();
        
        int numberToGuess = random.nextInt(100) + 1; // Random number between 1 and 100
        int numberOfTries = 0;
        int maxTries = 5; // Set maximum attempts allowed
        int guess = 0;
        boolean hasGuessedCorrectly = false;

        System.out.println("Welcome to the Number Guessing Game!");
        System.out.println("I'm thinking of a number between 1 and 100.");
        System.out.println("You have " + maxTries + " attempts to guess the correct number.");

        while (!hasGuessedCorrectly && numberOfTries < maxTries) {
            System.out.print("Enter your guess: ");
            guess = scanner.nextInt();
            numberOfTries++;

            if (guess < numberToGuess) {
                System.out.println("Too low, try again.");
            } else if (guess > numberToGuess) {
                System.out.println("Too high, try again.");
            } else {
                hasGuessedCorrectly = true;
                System.out.println("Congratulations! You've guessed the number " + numberToGuess + " in " + numberOfTries + " tries.");
            }
        }

        if (!hasGuessedCorrectly) {
            System.out.println("Sorry, you've reached the maximum number of tries. The correct number was " + numberToGuess + ".");
        }

        scanner.close();
    }
}
