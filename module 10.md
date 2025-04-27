EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node *next;
};

struct Node* createNode(int data) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    if (!newNode) {
        printf("Memory allocation failed!\n");
        return NULL;
    }
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}
void insertEnd(struct Node **head, int data) {
    struct Node *newNode = createNode(data);
    if (*head == NULL) {
        *head = newNode;
    } else {
        struct Node *temp = *head;
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = newNode;
    }
}

int searchElement(struct Node *head, int key) {
    struct Node *temp = head;
    while (temp != NULL) {
        if (temp->data == key) {
            return 1; 
        }
        temp = temp->next;
    }
    return 0; 
}

void displayList(struct Node *head) {
    struct Node *temp = head;
    if (temp == NULL) {
        printf("The list is empty.\n");
    } else {
        printf("Linked list elements: ");
        while (temp != NULL) {
            printf("%d ", temp->data);
            temp = temp->next;
        }
        printf("\n");
    }
}

int main() {
    struct Node *head = NULL;
    int element, key;
    insertEnd(&head, 10);
    insertEnd(&head, 20);
    insertEnd(&head, 30);
    insertEnd(&head, 40);
    insertEnd(&head, 50);
    displayList(head);
    printf("Enter the element to search: ");
    scanf("%d", &key);
    if (searchElement(head, key)) {
        printf("Element %d found in the list.\n", key);
    } else {
        printf("Element %d not found in the list.\n", key);
    }

    return 0;
}

```

Output:
Linked list elements: 10 20 30 40 50 
Enter the element to search: 30
Element 30 found in the list.




Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node *next;
};

struct Node* createNode(int data) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    if (!newNode) {
        printf("Memory allocation failed!\n");
        return NULL;
    }
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

void insertAtBeginning(struct Node **head, int data) {
    struct Node *newNode = createNode(data);
    newNode->next = *head;
    *head = newNode;
    printf("Node with data %d inserted at the beginning.\n", data);
}

void insertAtEnd(struct Node **head, int data) {
    struct Node *newNode = createNode(data);
    if (*head == NULL) {
        *head = newNode;
        printf("Node with data %d inserted at the end (first node in list).\n", data);
    } else {
        struct Node *temp = *head;
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = newNode;
        printf("Node with data %d inserted at the end.\n", data);
    }
}
void insertAtPosition(struct Node **head, int data, int position) {
    struct Node *newNode = createNode(data);
    if (position == 1) {
        insertAtBeginning(head, data); 
        return;
    }

    struct Node *temp = *head;
    int count = 1;
    while (temp != NULL && count < position - 1) {
        temp = temp->next;
        count++;
    }

    if (temp == NULL) {
        printf("Position is out of bounds.\n");
    } else {
        newNode->next = temp->next;
        temp->next = newNode;
        printf("Node with data %d inserted at position %d.\n", data, position);
    }
}

void displayList(struct Node *head) {
    struct Node *temp = head;
    if (temp == NULL) {
        printf("The list is empty.\n");
    } else {
        printf("Linked list elements: ");
        while (temp != NULL) {
            printf("%d ", temp->data);
            temp = temp->next;
        }
        printf("\n");
    }
}

int main() {
    struct Node *head = NULL;
    int choice, data, position;

    while (1) {
        printf("\nMenu:\n");
        printf("1. Insert at the beginning\n");
        printf("2. Insert at the end\n");
        printf("3. Insert at a specific position\n");
        printf("4. Display the linked list\n");
        printf("5. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter data to insert at the beginning: ");
                scanf("%d", &data);
                insertAtBeginning(&head, data);
                break;
            case 2:
                printf("Enter data to insert at the end: ");
                scanf("%d", &data);
                insertAtEnd(&head, data);
                break;
            case 3:
                printf("Enter data to insert: ");
                scanf("%d", &data);
                printf("Enter position to insert the node: ");
                scanf("%d", &position);
                insertAtPosition(&head, data, position);
                break;
            case 4:
                displayList(head);
                break;
            case 5:
                exit(0);
            default:
                printf("Invalid choice! Please try again.\n");
        }
    }

    return 0;
}

```

Output:
Menu:
1. Insert at the beginning
2. Insert at the end
3. Insert at a specific position
4. Display the linked list
5. Exit
Enter your choice: 1
Enter data to insert at the beginning: 10
Node with data 10 inserted at the beginning.

Menu:
1. Insert at the beginning
2. Insert at the end
3. Insert at a specific position
4. Display the linked list
5. Exit
Enter your choice: 2
Enter data to insert at the end: 20
Node with data 20 inserted at the end.

Menu:
1. Insert at the beginning
2. Insert at the end
3. Insert at a specific position
4. Display the linked list
5. Exit
Enter your choice: 3
Enter data to insert: 15
Enter position to insert the node: 2
Node with data 15 inserted at position 2.

Menu:
1. Insert at the beginning
2. Insert at the end
3. Insert at a specific position
4. Display the linked list
5. Exit
Enter your choice: 4
Linked list elements: 10 15 20


 
Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node *prev;
    struct Node *next;
};
struct Node* createNode(int data) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    if (!newNode) {
        printf("Memory allocation failed!\n");
        return NULL;
    }
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}
void insertEnd(struct Node **head, int data) {
    struct Node *newNode = createNode(data);
    if (*head == NULL) {
        *head = newNode;
        return;
    }

    struct Node *temp = *head;
    while (temp->next != NULL) {
        temp = temp->next;
    }
    temp->next = newNode;
    newNode->prev = temp;
}

void traverseForward(struct Node *head) {
    struct Node *temp = head;
    if (temp == NULL) {
        printf("The list is empty.\n");
        return;
    }
    
    printf("Forward traversal: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}
void traverseBackward(struct Node *head) {
    if (head == NULL) {
        printf("The list is empty.\n");
        return;
    }
    
    struct Node *temp = head;
    while (temp->next != NULL) {
        temp = temp->next;
    }

    printf("Backward traversal: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->prev;
    }
    printf("\n");
}

int main() {
    struct Node *head = NULL;
    int choice, data;
    while (1) {
        printf("\nMenu:\n");
        printf("1. Insert at the end\n");
        printf("2. Traverse forward\n");
        printf("3. Traverse backward\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter data to insert at the end: ");
                scanf("%d", &data);
                insertEnd(&head, data);
                break;
            case 2:
                traverseForward(head);
                break;
            case 3:
                traverseBackward(head);
                break;
            case 4:
                exit(0);
            default:
                printf("Invalid choice! Please try again.\n");
        }
    }

    return 0;
}

```


Output:
Menu:
1. Insert at the end
2. Traverse forward
3. Traverse backward
4. Exit
Enter your choice: 1
Enter data to insert at the end: 10

Menu:
1. Insert at the end
2. Traverse forward
3. Traverse backward
4. Exit
Enter your choice: 1
Enter data to insert at the end: 20

Menu:
1. Insert at the end
2. Traverse forward
3. Traverse backward
4. Exit
Enter your choice: 1
Enter data to insert at the end: 30

Menu:
1. Insert at the end
2. Traverse forward
3. Traverse backward
4. Exit
Enter your choice: 2
Forward traversal: 10 20 30

Menu:
1. Insert at the end
2. Traverse forward
3. Traverse backward
4. Exit
Enter your choice: 3
Backward traversal: 30 20 10




Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node *prev;
    struct Node *next;
};
struct Node* createNode(int data) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    if (!newNode) {
        printf("Memory allocation failed!\n");
        return NULL;
    }
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}
void insertAtBeginning(struct Node **head, int data) {
    struct Node *newNode = createNode(data);
    newNode->next = *head;
    if (*head != NULL) {
        (*head)->prev = newNode;
    }
    *head = newNode;
    printf("Node with data %d inserted at the beginning.\n", data);
}
void insertAtEnd(struct Node **head, int data) {
    struct Node *newNode = createNode(data);
    if (*head == NULL) {
        *head = newNode;
        printf("Node with data %d inserted at the end (first node in list).\n", data);
        return;
    }
    struct Node *temp = *head;
    while (temp->next != NULL) {
        temp = temp->next;
    }
    temp->next = newNode;
    newNode->prev = temp;
    printf("Node with data %d inserted at the end.\n", data);
}

void insertAtPosition(struct Node **head, int data, int position) {
    struct Node *newNode = createNode(data);
    if (position == 1) {
        insertAtBeginning(head, data);  // Insertion at the beginning
        return;
    }

    struct Node *temp = *head;
    int count = 1;
    while (temp != NULL && count < position - 1) {
        temp = temp->next;
        count++;
    }

    if (temp == NULL) {
        printf("Position is out of bounds.\n");
    } else {
        newNode->next = temp->next;
        newNode->prev = temp;
        if (temp->next != NULL) {
            temp->next->prev = newNode;
        }
        temp->next = newNode;
        printf("Node with data %d inserted at position %d.\n", data, position);
    }
}

void displayList(struct Node *head) {
    struct Node *temp = head;
    if (temp == NULL) {
        printf("The list is empty.\n");
        return;
    }
    printf("Doubly Linked List: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    struct Node *head = NULL;
    int choice, data, position;

    while (1) {
        printf("\nMenu:\n");
        printf("1. Insert at the beginning\n");
        printf("2. Insert at the end\n");
        printf("3. Insert at a specific position\n");
        printf("4. Display the list\n");
        printf("5. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter data to insert at the beginning: ");
                scanf("%d", &data);
                insertAtBeginning(&head, data);
                break;
            case 2:
                printf("Enter data to insert at the end: ");
                scanf("%d", &data);
                insertAtEnd(&head, data);
                break;
            case 3:
                printf("Enter data to insert: ");
                scanf("%d", &data);
                printf("Enter position to insert the node: ");
                scanf("%d", &position);
                insertAtPosition(&head, data, position);
                break;
            case 4:
                displayList(head);
                break;
            case 5:
                exit(0);
            default:
                printf("Invalid choice! Please try again.\n");
        }
    }

    return 0;
}
```

Output:
Menu:
1. Insert at the beginning
2. Insert at the end
3. Insert at a specific position
4. Display the list
5. Exit
Enter your choice: 1
Enter data to insert at the beginning: 10
Node with data 10 inserted at the beginning.

Menu:
1. Insert at the beginning
2. Insert at the end
3. Insert at a specific position
4. Display the list
5. Exit
Enter your choice: 2
Enter data to insert at the end: 20
Node with data 20 inserted at the end.

Menu:
1. Insert at the beginning
2. Insert at the end
3. Insert at a specific position
4. Display the list
5. Exit
Enter your choice: 3
Enter data to insert: 15
Enter position to insert the node: 2
Node with data 15 inserted at position 2.

Menu:
1. Insert at the beginning
2. Insert at the end
3. Insert at a specific position
4. Display the list
5. Exit
Enter your choice: 4
Doubly Linked List: 10 15 20



Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST




Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};
struct Node* createNode(int data) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    if (!newNode) {
        printf("Memory allocation failed!\n");
        return NULL;
    }
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

void insertEnd(struct Node **head, int data) {
    struct Node *newNode = createNode(data);
    if (*head == NULL) {
        *head = newNode;
        return;
    }
    struct Node *temp = *head;
    while (temp->next != NULL) {
        temp = temp->next;
    }
    temp->next = newNode;
}
void deleteElement(struct Node **head, int data) {
    if (*head == NULL) {
        printf("The list is empty, nothing to delete.\n");
        return;
    }
    if ((*head)->data == data) {
        struct Node *temp = *head;
        *head = (*head)->next; 
        free(temp);
        printf("Node with data %d deleted.\n", data);
        return;
    }
    struct Node *temp = *head;
    while (temp->next != NULL && temp->next->data != data) {
        temp = temp->next;
    }
    if (temp->next == NULL) {
        printf("Element %d not found in the list.\n", data);
        return;
    }
    struct Node *nodeToDelete = temp->next;
    temp->next = temp->next->next;  // Skip the node to be deleted
    free(nodeToDelete);  // Free the memory of the node to be deleted
    printf("Node with data %d deleted.\n", data);
}

void displayList(struct Node *head) {
    if (head == NULL) {
        printf("The list is empty.\n");
        return;
    }
    struct Node *temp = head;
    printf("Linked List: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    struct Node *head = NULL;
    int choice, data;

    while (1) {
        printf("\nMenu:\n");
        printf("1. Insert at the end\n");
        printf("2. Delete a given element\n");
        printf("3. Display the list\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter data to insert at the end: ");
                scanf("%d", &data);
                insertEnd(&head, data);
                break;
            case 2:
                printf("Enter data to delete from the list: ");
                scanf("%d", &data);
                deleteElement(&head, data);
                break;
            case 3:
                displayList(head);
                break;
            case 4:
                exit(0);
            default:
                printf("Invalid choice! Please try again.\n");
        }
    }

    return 0;
}
```


Output:

Menu:
1. Insert at the end
2. Delete a given element
3. Display the list
4. Exit
Enter your choice: 1
Enter data to insert at the end: 10

Menu:
1. Insert at the end
2. Delete a given element
3. Display the list
4. Exit
Enter your choice: 1
Enter data to insert at the end: 20

Menu:
1. Insert at the end
2. Delete a given element
3. Display the list
4. Exit
Enter your choice: 1
Enter data to insert at the end: 30

Menu:
1. Insert at the end
2. Delete a given element
3. Display the list
4. Exit
Enter your choice: 3
Linked List: 10 20 30 

Menu:
1. Insert at the end
2. Delete a given element
3. Display the list
4. Exit
Enter your choice: 2
Enter data to delete from the list: 20
Node with data 20 deleted.

Menu:
1. Insert at the end
2. Delete a given element
3. Display the list
4. Exit
Enter your choice: 3
Linked List: 10 30






Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





