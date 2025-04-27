

EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display stack elements using linked list.

Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};


void push(struct Node** top, int value) {

    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
   
    if (!newNode) {
        printf("Memory allocation failed!\n");
        return;
    }
 
    newNode->data = value;
    newNode->next = *top;
    

    *top = newNode;
}

void displayStack(struct Node* top) {
    if (top == NULL) {
        printf("Stack is empty!\n");
        return;
    }
    
    struct Node* current = top;
    printf("Stack elements: ");
    while (current != NULL) {
        printf("%d ", current->data);
        current = current->next;
    }
    
    printf("\n");
}


int main() {
    struct Node* stack = NULL;


    push(&stack, 10);
    push(&stack, 20);
    push(&stack, 30);
    push(&stack, 40);

    displayStack(stack);

    return 0;
}
```


Output:
Stack elements: 40 30 20 10



Result:
Thus, the program to display stack elements using linked list is verified successfully. 



EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
Aim:
To write a C program to pop an element from the given stack using liked list.

Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};
void push(struct Node** top, int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (!newNode) {
        printf("Memory allocation failed!\n");
        return;
    }
    newNode->data = value;
    newNode->next = *top;
    *top = newNode;
}


int pop(struct Node** top) {
    if (*top == NULL) {
        printf("Stack Underflow! Cannot pop from an empty stack.\n");
        return -1;  // Indicating failure
    }
    struct Node* temp = *top;
    int poppedValue = temp->data;
    *top = (*top)->next;  // Move top to the next node
    free(temp);           // Free memory of the popped node
    return poppedValue;
}
void displayStack(struct Node* top) {
    if (top == NULL) {
        printf("Stack is empty!\n");
        return;
    }
    printf("Stack elements: ");
    struct Node* current = top;
    while (current != NULL) {
        printf("%d ", current->data);
        current = current->next;
    }
    printf("\n");
}
int main() {
    struct Node* stack = NULL; 

    push(&stack, 10);
    push(&stack, 20);
    push(&stack, 30);
    push(&stack, 40);

    displayStack(stack);
    int popped = pop(&stack);
    displayStack(stack);

    return 0;
}
```

Output:

Stack elements: 40 30 20 10     
Popped element: 40
Stack elements: 30 20 10
Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display queue elements using linked list.
Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node* next;
};
void enqueue(struct Node** front, struct Node** rear, int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (!newNode) {
        printf("Memory allocation failed!\n");
        return;
    }
    newNode->data = value;
    newNode->next = NULL;

    if (*rear == NULL) { // Queue is empty
        *front = *rear = newNode;
    } else {
        (*rear)->next = newNode;
        *rear = newNode;
    }
}
void displayQueue(struct Node* front) {
    if (front == NULL) {
        printf("Queue is empty!\n");
        return;
    }

    printf("Queue elements: ");
    struct Node* current = front;
    while (current != NULL) {
        printf("%d ", current->data);
        current = current->next;
    }
    printf("\n");
}

int main() {
    struct Node* front = NULL; 
    struct Node* rear = NULL; 
    enqueue(&front, &rear, 10);
    enqueue(&front, &rear, 20);
    enqueue(&front, &rear, 30);
    enqueue(&front, &rear, 40);

    displayQueue(front);

    return 0;
}
```
Output:



 Queue elements: 10 20 30 40



Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim:
To write a C program to insert elements in queue using linked list

Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
Program:

```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node* next;
};

struct Node* createNode(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (!newNode) {
        printf("Memory allocation failed!\n");
        exit(1);
    }
    newNode->data = value;
    newNode->next = NULL;
    return newNode;
}
void enqueue(struct Node** front, struct Node** rear, int value) {
    struct Node* newNode = createNode(value);

    if (*rear == NULL) { // If the queue is empty
        *front = *rear = newNode;
    } else {
        (*rear)->next = newNode;
        *rear = newNode;
    }
    printf("%d inserted into the queue.\n", value);
}
void displayQueue(struct Node* front) {
    if (front == NULL) {
        printf("Queue is empty!\n");
        return;
    }

    printf("Queue elements: ");
    struct Node* temp = front;
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}


int main() {
    struct Node* front = NULL; 
    struct Node* rear = NULL;  
    int choice, value;

    do {
        printf("\n1. Insert (Enqueue)\n2. Display Queue\n3. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch(choice) {
            case 1:
                printf("Enter the value to insert: ");
                scanf("%d", &value);
                enqueue(&front, &rear, value);
                break;
            case 2:
                displayQueue(front);
                break;
            case 3:
                printf("Exiting...\n");
                break;
            default:
                printf("Invalid choice. Please choose again.\n");
        }
    } while (choice != 3);

    return 0;
}

```

Output:     

1. Insert (Enqueue)
2. Display Queue
3. Exit                      
Enter your choice: 1
Enter the value to insert: 10
10 inserted into the queue.

1. Insert (Enqueue)
2. Display Queue
3. Exit
Enter your choice: 1
Enter the value to insert: 20
20 inserted into the queue.

1. Insert (Enqueue)
2. Display Queue
3. Exit
Enter your choice: 2
Queue elements: 10 20


Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

Program:

```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node* next;
};

struct Node* createNode(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (!newNode) {
        printf("Memory allocation failed!\n");
        exit(1);
    }
    newNode->data = value;
    newNode->next = NULL;
    return newNode;
}

void enqueue(struct Node** front, struct Node** rear, int value) {
    struct Node* newNode = createNode(value);

    if (*rear == NULL) { 
        *front = *rear = newNode;
    } else {
        (*rear)->next = newNode;
        *rear = newNode;
    }
}
int peek(struct Node* front) {
    if (front == NULL) {
        printf("Queue is empty. Nothing to peek!\n");
        return -1; 
    }
    return front->data;
}

void displayQueue(struct Node* front) {
    if (front == NULL) {
        printf("Queue is empty!\n");
        return;
    }

    printf("Queue elements: ");
    struct Node* temp = front;
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}


int main() {
    struct Node* front = NULL;
    struct Node* rear = NULL;

    enqueue(&front, &rear, 100);
    enqueue(&front, &rear, 200);
    enqueue(&front, &rear, 300);

    displayQueue(front);

    int frontElement = peek(front);
    if (frontElement != -1) {
        printf("The front element (peek) is: %d\n", frontElement);
    }

    return 0;
}
```


Output:    

Queue elements: 100 200 300
The front element (peek) is: 100




Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


