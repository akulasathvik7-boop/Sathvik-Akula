# Sathvik-Akula
this is my second repository
<br>
Author-Sathvik Varma
import java.util.Random;
import java.util.Scanner;

public class GuessingGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();

        int lowerBound = 1;
        int upperBound = 100;
        int randomNumber = random.nextInt(upperBound - lowerBound + 1) + lowerBound; // Generates a number between 1 and 100
        int attempts = 0;
        int maxAttempts = 7; // User gets 7 attempts
        boolean hasGuessedCorrectly = false;

        System.out.println("Welcome to the Number Guessing Game!");
        System.out.println("I have generated a number between " + lowerBound + " and " + upperBound + ".");
        System.out.println("You have " + maxAttempts + " attempts to guess it.");

        while (attempts < maxAttempts && !hasGuessedCorrectly) {
            System.out.print("Enter your guess: ");
            int userGuess = scanner.nextInt();
            attempts++;

            if (userGuess == randomNumber) {
                hasGuessedCorrectly = true;
                System.out.println("Congratulations! You guessed the number in " + attempts + " attempts.");
            } else if (userGuess < randomNumber) {
                System.out.println("Too low! Try again. You have " + (maxAttempts - attempts) + " attempts left.");
            } else {
                System.out.println("Too high! Try again. You have " + (maxAttempts - attempts) + " attempts left.");
            }
        }

        if (!hasGuessedCorrectly) {
            System.out.println("You ran out of attempts! The correct number was: " + randomNumber);
        }

        scanner.close();
    }
}