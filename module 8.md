EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:

```
#include <stdio.h>

int main() {
    int number;
    char *words[] = {"zero", "one", "two", "three", "four",
                     "five", "six", "seven", "eight", "nine"};
    printf("Enter a number (0-9): ");
    scanf("%d", &number);
    if (number >= 0 && number <= 9) {
        printf("The word is: %s\n", words[number]);
    } else {
        printf("Invalid input! Please enter a number between 0 and 9.\n");
    }

    return 0;
}
```




Output:

![image](https://github.com/user-attachments/assets/d4e51471-1ceb-484d-b551-097f265d4e87)







Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:

```
#include <stdio.h>

int main() {
    char input[100];
    int freq[10] = {0}; 
    int i;
    printf("Enter digits: ");
    scanf("%s", input);

    for (i = 0; input[i] != '\0'; i++) {
        int digit = input[i] - '0';
        if (digit >= 0 && digit <= 3) {
            freq[digit]++;
        }
    }
    for (i = 0; i < 10; i++) {
        printf("%d ", freq[i]);
    }
    printf("\n");

    return 0;
}
```




Output:


![image](https://github.com/user-attachments/assets/e0774026-6e0d-4e45-943b-109c441fb931)







Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:

```
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
void swap(char *x, char *y) {
    char temp = *x;
    *x = *y;
    *y = temp;
}


void reverse(char str[], int l, int r) {
    while (l < r) {
        swap(&str[l], &str[r]);
        l++;
        r--;
    }
}


int nextPermutation(char str[]) {
    int len = strlen(str);
    int i = len - 2;

    while (i >= 0 && str[i] >= str[i + 1]) {
        i--;
    }

    if (i < 0) {
        return 0; // No more permutation
    }
    int j = len - 1;
    while (str[j] <= str[i]) {
        j--;
    }
    swap(&str[i], &str[j]);
    reverse(str, i + 1, len - 1);

    return 1;
}

int main() {
    char str[100];


    printf("Enter the string: ");
    scanf("%s", str);
    int len = strlen(str);
    for (int i = 0; i < len - 1; i++) {
        for (int j = i + 1; j < len; j++) {
            if (str[i] > str[j]) {
                swap(&str[i], &str[j]);
            }
        }
    }
    do {
        printf("%s\n", str);
    } while (nextPermutation(str));

    return 0;
}
```





Output:


![image](https://github.com/user-attachments/assets/7cd27c8f-2c2e-4a14-bf11-85563c3f1417)







Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:

```
#include <stdio.h>

int main() {
    int n, i, j;
    printf("Enter the value of n: ");
    scanf("%d", &n);
    for (i = 1; i <= n; i++) {
        // Inner loop for printing numbers
        for (j = 1; j <= i; j++) {
            printf("%d ", j);
        }
        printf("\n");
    }

    return 0;
}
```




Output:

![image](https://github.com/user-attachments/assets/c9066afe-cb22-4c2c-8310-8cb14154c630)






Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:

```
#include <stdio.h>
int calculateSquare() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    return num * num;
}

int main() {
    int result;
    result = calculateSquare();

   
    printf("Square of the number is: %d\n", result);

    return 0;
}

```




Output:

![image](https://github.com/user-attachments/assets/c9d5c7cc-aef8-4e59-8d18-2a43f357552e)







Result:
Thus, the program is verified successfully



























