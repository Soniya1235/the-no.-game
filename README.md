# the-no.-game
import java.util.Random;
import java.util.Scanner;

public class GuessTheNumberGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();
        int minnum = 1;
        int maxnum = 100;
        int maxattempt = 10;
        int totalscore = 0;
        System.out.println("Welcome to the number game");
        boolean playagain = true;
        while(playagain) {
            int numToGuess = random.nextInt(maxnum - minnum + 1) + minnum;
            int attempts = 0;
            int roundScore = maxattempt;
            System.out.println("I have selected a number between" + minnum + "and" + maxnum + ".");
            while (attempts < maxattempt) {
                System.out.println("Enter your guess:");
                int userGuess = scanner.nextInt();
                attempts++;
                if (userGuess == numToGuess) {
                    System.out.println("Congratulations! You guessed the number" + numToGuess + "Correctly in" + attempts + " attempts.");
                    break;
                } else if (userGuess < numToGuess) {
                    System.out.println("Too low. Try agian.");
                } else {
                    System.out.println("Too high. Try again.");
                }
                roundScore--;
                System.out.println("Attempts left:" + roundScore);
            }
            if (attempts == maxattempt) {
                System.out.println("Sorry, you have all your attempts. The correct number was" + numToGuess + ".");
            }
            totalscore++;
            System.out.println("Your totalscore is" + totalscore + ".");
            System.out.println("Do you want to play again? (yes/no):");
            String playagainInput = scanner.next();
            playagain = playagainInput.equalsIgnoreCase("yes");

        }
        System.out.println("Thanks for playing");

        }
    }



