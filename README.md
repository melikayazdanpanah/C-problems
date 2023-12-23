
Develop a void strcount(char string//) function which could printout the occurrence of each character in the given string. You are not
allowed to use any prepared C function. (10 Pts.)

Given Parameter
"123"
"hello"
"Hil!. hassan"
Output
1:1 2:1 3:1
e:l h:1 l:2 o:l
a:2 h:2 1:1 n:1 s:2 i:1 !:1  




```c
#include <stdio.h>

// Function to count occurrences of each character in a string
void strcount(const char string[]) {
    // Initialize an array to store character counts
    int charCount[256] = {0}; // Assuming ASCII characters

    // Iterate through the string
    for (int i = 0; string[i] != '\0'; ++i) {
        char currentChar = string[i];
        // Increment the count for the current character
        charCount[currentChar]++;
    }

    // Print the results
    for (int i = 0; i < 256; ++i) {
        if (charCount[i] > 0) {
            printf("%c:%d", i, charCount[i]);
            if (i < 255) {
                printf(",");
            }
        }
    }
    printf("\n");
}

int main() {
    char input1[] = "123";
    char input2[] = "hello";
    char input3[] = "Hil!. hassan";

    printf("Output for input1: ");
    strcount(input1);

    printf("Output for input2: ");
    strcount(input2);

    printf("Output for input3: ");
    strcount(input3);

    return 0;
}

```


Question: Write a line of code in C that matches a target string. You are not allowed to use any built-in C functions.

```c
#include <stdio.h>

// Function to check if a string contains a substring
int containsSubstring(const char string[], const char substring[]) {
    int i, j;
    for (i = 0; string[i] != '\0'; ++i) {
        for (j = 0; substring[j] != '\0'; ++j) {
            if (string[i + j] != substring[j]) {
                break;
            }
        }
        if (substring[j] == '\0') {
            return 1;
        }
    }
    return 0;
}

int main() {
    char string[] = "Hello, world!";
    char substring[] = "world";

    if (containsSubstring(string, substring)) {
        printf("Substring found!\n");
    } else {
        printf("Substring not found.\n");
    }

    return 0;
}

```

Q:The Tower of Hanoi is a classic mathematical puzzle that involves three rods and a number of disks of different sizes. The objective of the puzzle is to move the entire stack of disks from one rod to another, obeying the following simple rules:

Only one disk can be moved at a time.
Each move consists of taking the upper disk from one of the stacks and placing it on top of another stack i.e. a disk can only be moved if it is the uppermost disk on a stack.
No disk may be placed on top of a smaller disk.

```C
#include <stdio.h>

void towerOfHanoi(int n, char from_rod, char to_rod, char aux_rod) {
    if (n == 1) {
        printf("Move disk 1 from rod %c to rod %c\n", from_rod, to_rod);
        return;
    }
    towerOfHanoi(n - 1, from_rod, aux_rod, to_rod);
    printf("Move disk %d from rod %c to rod %c\n", n, from_rod, to_rod);
    towerOfHanoi(n - 1, aux_rod, to_rod, from_rod);
}

int main() {
    int n = 3; // Number of disks
    towerOfHanoi(n, 'A', 'C', 'B'); // A, B and C are the names of rods
    return 0;
}
```
