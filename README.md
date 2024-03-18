Faiza Khan
```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

// Function to generate a random number between min and max
int generateRandomNumber(int min, int max) {
    return min + rand() % (max - min + 1);
}

// Function to prompt the user for a guess and return the guess
int getUserGuess() {
    int guess;
    printf("Guess a number between 1 and 10: ");
    scanf("%d", &guess);
    return guess;
}

int main() {
    srand(time(NULL));

    const int minNumber = 1;
    const int maxNumber = 10;
    const int randomNumber = generateRandomNumber(minNumber, maxNumber);

    int numGuesses = 0;

    while (1) {
        int userGuess = getUserGuess();
        numGuesses++;

        if (userGuess == randomNumber) {
            printf("CORRECT! It took you %d guess%s.\n", numGuesses, (numGuesses == 1) ? "" : "es");
            break;
        } else if (userGuess < randomNumber) {
            printf("Your guess is too low.\n");
        } else {
            printf("Your guess is too high.\n");
        }
    }

    return 0;
}
```
