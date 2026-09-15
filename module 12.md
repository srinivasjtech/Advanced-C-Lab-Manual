# EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.

## Aim:
To write a C program to display stack elements using linked list.

## Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
## Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* head = NULL;

void display() {
    struct Node* p = head;
    if (p == NULL) {
        printf("Linked list is empty.\n");
        return;
    }
    printf("Linked list elements are:\n");
    while (p != NULL) {
        printf("%d ", p->data);
        p = p->next;
    }
    printf("\n");
}

int main() {
    struct Node* first = (struct Node*)malloc(sizeof(struct Node));
    struct Node* second = (struct Node*)malloc(sizeof(struct Node));
    struct Node* third = (struct Node*)malloc(sizeof(struct Node));

    first->data = 10;
    second->data = 20;
    third->data = 30;

    first->next = second;
    second->next = third;
    third->next = NULL;

    head = first;

    display();

    return 0;
}
```

## Output:

<img width="441" height="149" alt="651988303-1889c34d-550e-41fb-be2c-aba16839c9ba" src="https://github.com/user-attachments/assets/a1224185-cf07-4f12-98d7-1335c6627f5a" />


## Result:
Thus, the program to display stack elements using linked list is verified successfully. 



# EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING LINKED LIST.

## Aim:
To write a C program to pop an element from the given stack using liked list.

## Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
## Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* head = NULL;

void push(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (newNode == NULL) {
        printf("Memory allocation failed.\n");
        return;
    }
    newNode->data = value;
    newNode->next = head;
    head = newNode;
}

void pop() {
    if (head == NULL) {
        printf("Stack is empty.\n");
    } else {
        struct Node* temp = head;
        printf("Popped element: %d\n", head->data);
        head = head->next;
        free(temp);
    }
}

void display() {
    struct Node* p = head;
    if (p == NULL) {
        printf("Stack is empty.\n");
    } else {
        printf("Stack elements are:\n");
        while (p != NULL) {
            printf("%d ", p->data);
            p = p->next;
        }
        printf("\n");
    }
}

int main() {
    int choice, value;

    while (1) {
        printf("\n1. Push\n2. Pop\n3. Display\n4. Exit\nEnter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter value to push: ");
                scanf("%d", &value);
                push(value);
                break;
            case 2:
                pop();
                break;
            case 3:
                display();
                break;
            case 4:
                return 0;
            default:
                printf("Invalid choice. Please try again.\n");
        }
    }
}


```

## Output:

<img width="330" height="621" alt="651988610-e624e6da-f510-4a1f-a088-91675d712f48" src="https://github.com/user-attachments/assets/638e5f59-1da5-4b19-b384-eca629e008bc" />


## Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
# EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.

## Aim:
To write a C program to display queue elements using linked list.

## Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
## Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* front = NULL;
struct Node* rear = NULL;

void enqueue(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (newNode == NULL) {
        printf("Memory allocation failed.\n");
        return;
    }
    newNode->data = value;
    newNode->next = NULL;
    if (front == NULL && rear == NULL) {
        front = rear = newNode;
    } else {
        rear->next = newNode;
        rear = newNode;
    }
}

void display() {
    if (front == NULL) {
        printf("Queue is empty.\n");
    } else {
        struct Node* temp = front;
        printf("Queue elements are:\n");
        while (temp != NULL) {
            printf("%d ", temp->data);
            temp = temp->next;
        }
        printf("\n");
    }
}

int main() {
    int choice, value;

    while (1) {
        printf("\n1. Enqueue\n2. Display\n3. Exit\nEnter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter value to enqueue: ");
                scanf("%d", &value);
                enqueue(value);
                break;
            case 2:
                display();
                break;
            case 3:
                return 0;
            default:
                printf("Invalid choice. Try again.\n");
        }
    }
}


```

## Output:

<img width="399" height="721" alt="651988857-426f5a64-61d3-4d6a-9a85-2c4f18647c36" src="https://github.com/user-attachments/assets/27662b6b-f2fc-4fa2-8e25-8d7cc6a10219" />


## Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
# EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

## Aim:
To write a C program to insert elements in queue using linked list

## Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
## Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* front = NULL;
struct Node* rear = NULL;

void enqueue(int value) {
    struct Node* p = (struct Node*)malloc(sizeof(struct Node));
    if (p == NULL) {
        printf("Memory allocation failed.\n");
        return;
    }
    p->data = value;
    p->next = NULL;

    if (front == NULL && rear == NULL) {
        front = rear = p;
    } else {
        rear->next = p;
        rear = p;
    }
}

void display() {
    if (front == NULL) {
        printf("Queue is empty.\n");
    } else {
        struct Node* temp = front;
        printf("Queue elements are:\n");
        while (temp != NULL) {
            printf("%d ", temp->data);
            temp = temp->next;
        }
        printf("\n");
    }
}

int main() {
    int choice, value;

    while (1) {
        printf("\n1. Enqueue\n2. Display\n3. Exit\nEnter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter value to enqueue: ");
                scanf("%d", &value);
                enqueue(value);
                break;
            case 2:
                display();
                break;
            case 3:
                return 0;
            default:
                printf("Invalid choice. Please try again.\n");
        }
    }
}


```

## Output:

<img width="345" height="840" alt="651989076-b5643cd1-1a14-409c-905a-4124da77f660" src="https://github.com/user-attachments/assets/4a4b4c77-ca0e-4fc0-be1b-ef7e5482d876" />


## Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



# EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.

## Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

## Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

## Program:

```c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* front = NULL;
struct Node* rear = NULL;

void enqueue(int value) {
    struct Node* p = (struct Node*)malloc(sizeof(struct Node));
    if (p == NULL) {
        printf("Memory allocation failed.\n");
        return;
    }
    p->data = value;
    p->next = NULL;

    if (front == NULL && rear == NULL) {
        front = rear = p;
    } else {
        rear->next = p;
        rear = p;
    }
}

void display() {
    if (front == NULL) {
        printf("Queue is empty.\n");
    } else {
        struct Node* temp = front;
        printf("Queue elements are:\n");
        while (temp != NULL) {
            printf("%d ", temp->data);
            temp = temp->next;
        }
        printf("\n");
    }
}

int peek() {
    if (front == NULL) {
        printf("Queue is empty.\n");
        return -1;  // Return -1 to indicate an empty queue
    } else {
        return front->data;
    }
}

int main() {
    int choice, value;

    while (1) {
        printf("\n1. Enqueue\n2. Display\n3. Peek\n4. Exit\nEnter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter value to enqueue: ");
                scanf("%d", &value);
                enqueue(value);
                break;
            case 2:
                display();
                break;
            case 3:
                printf("Front element is: %d\n", peek());
                break;
            case 4:
                return 0;
            default:
                printf("Invalid choice. Please try again.\n");
        }
    }
}



```

## Output:

<img width="300" height="819" alt="651989359-002e418d-9f33-4b58-8091-417fa4339fcc" src="https://github.com/user-attachments/assets/2e9d441e-d6f7-420d-baf3-0b0bc0b904c7" />


## Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


