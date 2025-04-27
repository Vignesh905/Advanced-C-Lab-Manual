EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:
```
#include <stdio.h>
#define MAX 5 

struct Stack {
    int arr[MAX];
    int top;
};
void initializeStack(struct Stack *stack) {
    stack->top = -1; // Stack is initially empty
}

int isFull(struct Stack *stack) {
    return stack->top == MAX - 1;
}
int isEmpty(struct Stack *stack) {
    return stack->top == -1;
}
void push(struct Stack *stack, int value) {
    if (isFull(stack)) {
        printf("Stack Overflow! Cannot push %d\n", value);
    } else {
        stack->arr[++stack->top] = value;
        printf("Pushed %d into stack\n", value);
    }
}

int pop(struct Stack *stack) {
    if (isEmpty(stack)) {
        printf("Stack Underflow! No elements to pop.\n");
        return -1; 
    } else {
        return stack->arr[stack->top--];
    }
}

int peek(struct Stack *stack) {
    if (isEmpty(stack)) {
        printf("Stack is empty!\n");
        return -1;
    } else {
        return stack->arr[stack->top];
    }
}

void displayStack(struct Stack *stack) {
    if (isEmpty(stack)) {
        printf("Stack is empty!\n");
    } else {
        printf("Stack elements are: \n");
        for (int i = 0; i <= stack->top; i++) {
            printf("%d ", stack->arr[i]);
        }
        printf("\n");
    }
}

int main() {
    struct Stack stack;
    int value;
    initializeStack(&stack);

    push(&stack, 10);
    push(&stack, 20);
    push(&stack, 30);
    push(&stack, 40);
    push(&stack, 50);
    displayStack(&stack);

    push(&stack, 60);

    value = pop(&stack);
    printf("Popped value: %d\n", value);
    displayStack(&stack);
    value = peek(&stack);
    printf("Top element: %d\n", value);

    return 0;
}

```

Output:
![image](https://github.com/user-attachments/assets/4cb2a418-1e16-4500-8983-7fb2e771202d)





Result:
Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:
```
#include <stdio.h>
#define MAX 5 

struct Stack {
    int arr[MAX];
    int top;
};

void initializeStack(struct Stack *stack) {
    stack->top = -1; // Stack is initially empty
}

int isFull(struct Stack *stack) {
    return stack->top == MAX - 1;
}
void push(struct Stack *stack, int value) {
    if (isFull(stack)) {
        printf("Stack Overflow! Cannot push %d\n", value);
    } else {
        stack->arr[++stack->top] = value; 
        printf("Pushed %d into stack\n", value);
    }
}
void displayStack(struct Stack *stack) {
    if (stack->top == -1) {
        printf("Stack is empty!\n");
    } else {
        printf("Stack elements are: \n");
        for (int i = 0; i <= stack->top; i++) {
            printf("%d ", stack->arr[i]);
        }
        printf("\n");
    }
}

int main() {
    struct Stack stack;
    int value;
    initializeStack(&stack);

    push(&stack, 10);
    push(&stack, 20);
    push(&stack, 30);
    push(&stack, 40);
    push(&stack, 50);

 
    displayStack(&stack);
    push(&stack, 60);

    return 0;
}
```


Output:
![image](https://github.com/user-attachments/assets/96c53cd3-0ccb-4231-a505-afe7f1a902fa)




Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:
```
#include <stdio.h>
#define MAX 5
struct Queue {
    int arr[MAX];
    int front;
    int rear;
};

void initializeQueue(struct Queue *queue) {
    queue->front = -1;
    queue->rear = -1;
}

int isFull(struct Queue *queue) {
    return queue->rear == MAX - 1;
}

int isEmpty(struct Queue *queue) {
    return queue->front == -1 || queue->front > queue->rear;
}

void enqueue(struct Queue *queue, int value) {
    if (isFull(queue)) {
        printf("Queue Overflow! Cannot enqueue %d\n", value);
    } else {
        if (queue->front == -1) {
            queue->front = 0; // First element being added
        }
        queue->arr[++queue->rear] = value;
        printf("Enqueued %d into the queue\n", value);
    }
}

int dequeue(struct Queue *queue) {
    if (isEmpty(queue)) {
        printf("Queue Underflow! No elements to dequeue\n");
        return -1; // Return -1 to indicate error
    } else {
        int dequeuedValue = queue->arr[queue->front++];
        if (queue->front > queue->rear) {
            // Reset the queue if it becomes empty
            queue->front = queue->rear = -1;
        }
        return dequeuedValue;
    }
}
void displayQueue(struct Queue *queue) {
    if (isEmpty(queue)) {
        printf("Queue is empty!\n");
    } else {
        printf("Queue elements are: \n");
        for (int i = queue->front; i <= queue->rear; i++) {
            printf("%d ", queue->arr[i]);
        }
        printf("\n");
    }
}

int main() {
    struct Queue queue;
    int value;

 
    initializeQueue(&queue);

    enqueue(&queue, 10);
    enqueue(&queue, 20);
    enqueue(&queue, 30);
    enqueue(&queue, 40);
    enqueue(&queue, 50);
    displayQueue(&queue);
    enqueue(&queue, 60);
    value = dequeue(&queue);
    printf("Dequeued value: %d\n", value);
    displayQueue(&queue);

    return 0;
}
```


Output:

![image](https://github.com/user-attachments/assets/b3505cc0-14c2-485b-b8be-ef54245610c7)



Result:
Thus, the program to display queue elements using array is verified successfully.


 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:

```
#include <stdio.h>
#define MAX 5 


struct Queue {
    int arr[MAX];
    int front;
    int rear;
};


void initializeQueue(struct Queue *queue) {
    queue->front = -1;
    queue->rear = -1;
}

int isFull(struct Queue *queue) {
    return queue->rear == MAX - 1;
}

int isEmpty(struct Queue *queue) {
    return queue->front == -1 || queue->front > queue->rear;
}


void enqueue(struct Queue *queue, int value) {
    if (isFull(queue)) {
        printf("Queue Overflow! Cannot enqueue %d\n", value);
    } else {
        if (queue->front == -1) {
            queue->front = 0; // First element being added
        }
        queue->arr[++queue->rear] = value; // Add element at rear
        printf("Enqueued %d into the queue\n", value);
    }
}


void displayQueue(struct Queue *queue) {
    if (isEmpty(queue)) {
        printf("Queue is empty!\n");
    } else {
        printf("Queue elements are: \n");
        for (int i = queue->front; i <= queue->rear; i++) {
            printf("%d ", queue->arr[i]);
        }
        printf("\n");
    }
}

int main() {
    struct Queue queue;
    int value;
    initializeQueue(&queue);

    enqueue(&queue, 10);
    enqueue(&queue, 20);
    enqueue(&queue, 30);
    enqueue(&queue, 40);
    enqueue(&queue, 50);

 
    displayQueue(&queue);
    enqueue(&queue, 60);

    return 0;
}

```

Output:

![image](https://github.com/user-attachments/assets/7209ca95-08dc-4d71-9d79-11a847957b65)


Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:

```
#include <stdio.h>
#define MAX 5 

struct Queue {
    int arr[MAX];
    int front;
    int rear;
};

void initializeQueue(struct Queue *queue) {
    queue->front = -1;
    queue->rear = -1;
}
int isFull(struct Queue *queue) {
    return queue->rear == MAX - 1;
}

int isEmpty(struct Queue *queue) {
    return queue->front == -1 || queue->front > queue->rear;
}

void enqueue(struct Queue *queue, int value) {
    if (isFull(queue)) {
        printf("Queue Overflow! Cannot enqueue %d\n", value);
    } else {
        if (queue->front == -1) {
            queue->front = 0; // First element being added
        }
        queue->arr[++queue->rear] = value; // Add element at rear
        printf("Enqueued %d into the queue\n", value);
    }
}

int dequeue(struct Queue *queue) {
    if (isEmpty(queue)) {
        printf("Queue Underflow! No elements to dequeue\n");
        return -1; // Return -1 to indicate error
    } else {
        int dequeuedValue = queue->arr[queue->front];
        queue->front++; 
        if (queue->front > queue->rear) {
           
            queue->front = queue->rear = -1;
        }
        return dequeuedValue;
    }
}

void displayQueue(struct Queue *queue) {
    if (isEmpty(queue)) {
        printf("Queue is empty!\n");
    } else {
        printf("Queue elements are: \n");
        for (int i = queue->front; i <= queue->rear; i++) {
            printf("%d ", queue->arr[i]);
        }
        printf("\n");
    }
}

int main() {
    struct Queue queue;
    int value;


    initializeQueue(&queue);
    enqueue(&queue, 10);
    enqueue(&queue, 20);
    enqueue(&queue, 30);
    enqueue(&queue, 40);
    enqueue(&queue, 50);

    displayQueue(&queue);
    value = dequeue(&queue);
    printf("Dequeued value: %d\n", value);
    displayQueue(&queue);

    return 0;
}

```

Output:

![image](https://github.com/user-attachments/assets/a5155657-e9de-4f21-9a83-2c1e1bf3a810)



Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
