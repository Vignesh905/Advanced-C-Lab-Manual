

EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
Aim:
To write a C program to create a function to find the greatest number

Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
Program:
```
#include <stdio.h>

int findGreatest(int arr[], int size) {
    int greatest = arr[0];  // Assume the first element is the greatest

    for (int i = 1; i < size; i++) {
        if (arr[i] > greatest) {
            greatest = arr[i];  // Update greatest if a larger number is found
        }
    }
    return greatest;
}

int main() {
    int n;
    printf("Enter the number of elements: ");
    scanf("%d", &n);

    int arr[n];
    printf("Enter the elements:\n");
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    int greatest = findGreatest(arr, n);
    printf("The greatest number is: %d\n", greatest);

    return 0;
}
```

Output:
Enter the number of elements: 5      
Enter the elements:             
10
20
5
30
25
The greatest number is: 30


Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
Program:
```
#include <stdio.h>

int bitwiseAND(int a, int b) {
    return a & b;
}

int bitwiseOR(int a, int b) {
    return a | b;
}
int bitwiseXOR(int a, int b) {
    return a ^ b;
}

int main() {
    printf("Enter two numbers: ");
    scanf("%d %d", &num1, &num2);
    int andResult = bitwiseAND(num1, num2);
    int orResult = bitwiseOR(num1, num2);
    int xorResult = bitwiseXOR(num1, num2);
    printf("AND operation result: %d\n", andResult);
    printf("OR operation result: %d\n", orResult);
    printf("XOR operation result: %d\n", xorResult);

    return 0;
}
```


Output:
Enter two numbers: 5 3  
AND operation result: 1   
OR operation result: 7    
XOR operation result: 6    


Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
Aim:
To write a C program to write the logic for the requests

Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
int add(int a, int b) {
    return a + b;
}

int subtract(int a, int b) {
    return a - b;
}

int multiply(int a, int b) {
    return a * b;
}

float divide(int a, int b) {
    if (b == 0) {
        printf("Error! Division by zero is not allowed.\n");
        return -1;  // Return -1 to indicate an error
    }
    return (float)a / b;
}

int findGreatest(int a, int b) {
    return (a > b) ? a : b;
}

void displayMenu() {
    printf("\nMenu:\n");
    printf("1. Add two numbers\n");
    printf("2. Subtract two numbers\n");
    printf("3. Multiply two numbers\n");
    printf("4. Divide two numbers\n");
    printf("5. Find the greatest number\n");
    printf("6. Exit\n");
}

int main() {
    int choice, num1, num2;

    while (1) {
        displayMenu();
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter two numbers: ");
                scanf("%d %d", &num1, &num2);
                printf("Result: %d\n", add(num1, num2));
                break;
            case 2:
                printf("Enter two numbers: ");
                scanf("%d %d", &num1, &num2);
                printf("Result: %d\n", subtract(num1, num2));
                break;
            case 3:
                printf("Enter two numbers: ");
                scanf("%d %d", &num1, &num2);
                printf("Result: %d\n", multiply(num1, num2));
                break;
            case 4:
                printf("Enter two numbers: ");
                scanf("%d %d", &num1, &num2);
                float result = divide(num1, num2);
                if (result != -1) {
                    printf("Result: %.2f\n", result);
                }
                break;
            case 5:
                printf("Enter two numbers: ");
                scanf("%d %d", &num1, &num2);
                printf("The greatest number is: %d\n", findGreatest(num1, num2));
                break;
            case 6:
                printf("Exiting the program.\n");
                exit(0);  // Exit the program
            default:
                printf("Invalid choice! Please try again.\n");
        }
    }

    return 0;
}

```

Output:
Menu:
1. Add two numbers
2. Subtract two numbers
3. Multiply two numbers
4. Divide two numbers
5. Find the greatest number
6. Exit
Enter your choice: 1
Enter two numbers: 5 3
Result: 8

Menu:
1. Add two numbers
2. Subtract two numbers
3. Multiply two numbers
4. Divide two numbers
5. Find the greatest number
6. Exit
Enter your choice: 4
Enter two numbers: 10 2
Result: 5.00

Menu:
1. Add two numbers
2. Subtract two numbers
3. Multiply two numbers
4. Divide two numbers
5. Find the greatest number
6. Exit
Enter your choice: 5
Enter two numbers: 5 8
The greatest number is: 8

Menu:
1. Add two numbers
2. Subtract two numbers
3. Multiply two numbers
4. Divide two numbers
5. Find the greatest number
6. Exit
Enter your choice: 6
Exiting the program.



Result:
Thus, the program to write the logic for the requests is verified successfully.


 
EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
Aim:
To write a C program print the sum of the integers in the array.

Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



Program:
```
#include <stdio.h>
int sumOfArray(int arr[], int size)
 {
    int sum = 0;
    for (int i = 0; i < size; i++) {
        sum += arr[i];  // Add each element to sum
    }
    return sum;
}

int main() {
    int n;
    printf("Enter the number of elements in the array: ");
    scanf("%d", &n);

    int arr[n];
    printf("Enter %d integers:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    int sum = sumOfArray(arr, n);
    printf("The sum of the integers in the array is: %d\n", sum);

    return 0;
}

```

Output:

Enter the number of elements in the array: 5
Enter 5 integers:
1 2 3 4 5
The sum of the integers in the array is: 15


 


Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 

EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A      SENTENCE
Aim:

To write a C program that counts the number of words in a given sentence.

Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



Program:
```
#include <stdio.h>
#include <ctype.h>
int countWords(char sentence[]) {
    int count = 0, i = 0;
    while (sentence[i] != '\0') {
        // Skip any spaces
        while (sentence[i] == ' ' || sentence[i] == '\t') {
            i++;
        }
        if (sentence[i] != '\0') {
            count++;
            while (sentence[i] != ' ' && sentence[i] != '\t' && sentence[i] != '\0') {
                i++;
            }
        }
    }
    return count;
}

int main() {
    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);
    int wordCount = countWords(sentence);
    printf("The number of words in the sentence is: %d\n", wordCount);

    return 0;
}
```

Output:
Enter a sentence: Hello world, this is a test sentence.
The number of words in the sentence is: 7




Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
