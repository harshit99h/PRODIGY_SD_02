
import java.util.InputMismatchException;
import java.util.Random;
import java.util.Scanner;

public class GuessingGame {
    private static final int MIN_NUMBER = 1;
    private static final int MAX_NUMBER = 100;

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();
        int randomNumber = random.nextInt(MAX_NUMBER - MIN_NUMBER + 1) + MIN_NUMBER;
        int attempts = 0;
        boolean hasGuessedCorrectly = false;

        System.out.println("Welcome to the Guessing Game!");
        System.out.println("I have generated a random number between " + MIN_NUMBER + " and " + MAX_NUMBER + ".");
        System.out.println("Try to guess it!");

        while (!hasGuessedCorrectly) {
            int guess = getUserGuess(scanner);
            attempts++;
            hasGuessedCorrectly = checkGuess(guess, randomNumber);
        }

        System.out.println("Congratulations! You've guessed the correct number.");
        System.out.println("It took you " + attempts + " attempts to guess the correct number.");
        scanner.close();
    }

    private static int getUserGuess(Scanner scanner) {
        int guess = 0;
        boolean validInput = false;

        while (!validInput) {
            System.out.print("Enter your guess: ");
            try {
                guess = scanner.nextInt();
                validInput = true;
            } catch (InputMismatchException e) {
                System.out.println("Invalid input. Please enter a valid integer.");
                scanner.next();
            }
        }
        return guess;
    }

    private static boolean checkGuess(int guess, int randomNumber) {
        if (guess < randomNumber) {
            System.out.println("Too low! Try again.");
            return false;
        } else if (guess > randomNumber) {
            System.out.println("Too high! Try again.");
            return false;
        } else {
            return true;
        }
    }
}
