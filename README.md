# Guess-A-Number
This interactive game prompts users to guess a number, tracking attempts and giving feedback. It showcases loops, conditionals, input handling, and random number generation in C.

#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main(){ // Start of main.
    srand(time(NULL)); // Initializes the random number generator with the current time.


    const unsigned int random = 1 + rand() % 10; // Generates a random number between 1 and 10.
    int guess = 0; // Initializes the variable to store user's guess.
    int amount_guesses = 0; //Initializes the variable to count the number of guesses.


    while (random != guess){ // Is a loop until the user's guess matches the random number.
        printf("Guess a number between 1 and 10. Your guess: "); // Prompts the user to guess a number.
        scanf("%d", &guess); // Reads the user's input and stores it in the 'guess' variable.
        amount_guesses++; // Increments the count of guesses.

        if (guess == random){ // Checks if the user's guess matches the random number.
            if (amount_guesses == 1){ // Checks if it took the user only one guess.
                // Prints a message indicating the user guessed correctly in one attempt.
                printf("CORRECT! It took you %d guess.\n", amount_guesses);
            } else{ // If the user took more than one guess.
                // Prints a message indicating the number of guesses it took to guess correctly.
                printf("CORRECT! It took you %d guesses.\n", amount_guesses);
            }
            break; // Exits the loop.
        } if (guess < random){ // If the user's guess is lower than the random number.
            printf("Your guess is too low.\n"); // Prints a message indicating the guess is too low.
        } else { // If the user's guess is higher than the random number.
            printf("Your guess is too high.\n"); // Prints a message indicating the guess is too high.
        }
    }
    return 0; // Returns successful completion.
}
