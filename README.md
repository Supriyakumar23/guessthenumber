# guessthenumber
game
import java.util.Random;
import java.util.Scanner;

public class GuessTheNumber {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();

        int secretNumber = random.nextInt(100) + 1;
        int maxAttempts = 5;
        int attempts = 0;
        int guess;

        System.out.println("Welcome to Guess the Number!");
        System.out.println("I have selected a number between 1 and 100.");
        System.out.println("You have " + maxAttempts + " attempts to guess the correct number.");

        while (attempts < maxAttempts) {
            System.out.print("Enter your guess: ");
            guess = scanner.nextInt();
            attempts++;

            if (guess == secretNumber) {
                System.out.println("Congratulations! You guessed the correct number.");
                System.out.println("You took " + attempts + " attempts.");
                return;
            } else if (guess < secretNumber) {
                System.out.println("Too low. Try again!");
            } else {
                System.out.println("Too high. Try again!");
            }
        }

        System.out.println("Sorry, you've run out of attempts.");
        System.out.println("The secret number was " + secretNumber + ". Better luck next time!");
    }
}
