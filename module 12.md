

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

// Step 1: Define structure
struct Node
{
    int data;
    struct Node *next;
};

// Step 2: Global head (top of stack)
struct Node *head = NULL;

// Function to push elements (for creating stack)
void push(int value)
{
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));

    if (newNode == NULL)
    {
        printf("Stack Overflow. Memory not allocated.\n");
        return;
    }

    newNode->data = value;
    newNode->next = head;
    head = newNode;
}

// Step 3: Display function
void display()
{
    // Step 4: Initialize pointer
    struct Node *p = head;

    if (p == NULL)
    {
        printf("Stack is empty.\n");
        return;
    }

    printf("Stack elements (Top to Bottom):\n");

    // Step 5: Traverse list
    while (p != NULL)
    {
        // Step 6: Print data
        printf("%d\n", p->data);

        // Step 7: Move to next node
        p = p->next;
    }
}

int main()
{
    int n, value;

    printf("Enter number of elements to push: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++)
    {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);
        push(value);
    }

    display();

    return 0;
}
```

Output:

<img width="815" height="390" alt="image" src="https://github.com/user-attachments/assets/3a73cb00-1113-45b0-9d68-f09ddc7f2847" />


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

// Define structure
struct Node
{
    int data;
    struct Node *next;
};

// Global head (top of stack)
struct Node *head = NULL;

// Push function (for creating stack)
void push(int value)
{
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));

    if (newNode == NULL)
    {
        printf("Stack Overflow.\n");
        return;
    }

    newNode->data = value;
    newNode->next = head;
    head = newNode;
}

// Pop function
void pop()
{
    // Step 1 & 2: Check for empty stack
    if (head == NULL)
    {
        printf("Stack is empty.\n");
        return;
    }

    // Step 3 & 4: Remove top element
    struct Node *temp = head;
    printf("Popped element: %d\n", head->data);

    head = head->next;
    free(temp);
}

// Display function
void display()
{
    struct Node *p = head;

    if (p == NULL)
    {
        printf("Stack is empty.\n");
        return;
    }

    printf("Stack elements (Top to Bottom):\n");
    while (p != NULL)
    {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main()
{
    int n, value;

    printf("Enter number of elements to push: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++)
    {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);
        push(value);
    }

    printf("\nBefore Pop Operation:\n");
    display();

    printf("\nPerforming Pop Operation:\n");
    pop();

    printf("\nAfter Pop Operation:\n");
    display();

    return 0;
}
```

Output:

<img width="815" height="677" alt="image" src="https://github.com/user-attachments/assets/fe83d728-d3fa-46b7-829c-1f149f113698" />

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

// Define structure
struct Node
{
    int data;
    struct Node *next;
};

// Front and Rear pointers
struct Node *front = NULL;
struct Node *rear = NULL;

// Enqueue function (to create queue)
void enqueue(int value)
{
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));

    if (newNode == NULL)
    {
        printf("Queue Overflow.\n");
        return;
    }

    newNode->data = value;
    newNode->next = NULL;

    if (rear == NULL)
    {
        front = rear = newNode;
    }
    else
    {
        rear->next = newNode;
        rear = newNode;
    }
}

// Display function
void display()
{
    // Step 1: Check if queue is empty
    if (front == NULL)
    {
        printf("Queue is empty.\n");
        return;
    }

    struct Node *temp = front;

    printf("Queue elements (Front to Rear):\n");

    // Step 2, 3, 4: Traverse and print
    while (temp != NULL)
    {
        printf("%d\n", temp->data);
        temp = temp->next;
    }

    // Step 5: End function
}

int main()
{
    int n, value;

    printf("Enter number of elements to enqueue: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++)
    {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);
        enqueue(value);
    }

    display();

    return 0;
}
```

Output:

<img width="822" height="367" alt="image" src="https://github.com/user-attachments/assets/364f0598-2ce6-45e8-bb6e-b0fbca0c9da8" />

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

// Define structure
struct Node
{
    int data;
    struct Node *next;
};

// Front and Rear pointers
struct Node *front = NULL;
struct Node *rear = NULL;

// Enqueue function
void enqueue(int value)
{
    // Step 1: Allocate memory
    struct Node *p = (struct Node*)malloc(sizeof(struct Node));

    if (p == NULL)
    {
        printf("Queue Overflow.\n");
        return;
    }

    // Step 2: Set data and next pointer
    p->data = value;
    p->next = NULL;

    // Step 3: Check if queue is empty
    if (front == NULL)
    {
        // Step 4: First node
        front = rear = p;
    }
    else
    {
        // Step 5: Link new node at rear
        rear->next = p;
        rear = p;
    }

    // Step 6: End of operation
}

// Display function
void display()
{
    if (front == NULL)
    {
        printf("Queue is empty.\n");
        return;
    }

    struct Node *temp = front;
    printf("Queue elements (Front to Rear):\n");

    while (temp != NULL)
    {
        printf("%d\n", temp->data);
        temp = temp->next;
    }
}

int main()
{
    int n, value;

    printf("Enter number of elements to insert: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++)
    {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);
        enqueue(value);
    }

    display();

    return 0;
}
```

Output:

<img width="813" height="381" alt="image" src="https://github.com/user-attachments/assets/2d1da8ec-678c-4a2c-9363-d26161803f81" />

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

// Define structure
struct Node
{
    int data;
    struct Node *next;
};

// Front and Rear pointers
struct Node *front = NULL;
struct Node *rear = NULL;

// Enqueue function (for creating queue)
void enqueue(int value)
{
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));

    if (newNode == NULL)
    {
        printf("Queue Overflow.\n");
        return;
    }

    newNode->data = value;
    newNode->next = NULL;

    if (front == NULL)
    {
        front = rear = newNode;
    }
    else
    {
        rear->next = newNode;
        rear = newNode;
    }
}

// Peek function
int peek()
{
    // Step 1: Check if queue is empty
    if (front == NULL)
    {
        printf("Queue is empty.\n");
        return -1;  // Error value
    }

    // Step 2: Return front element
    return front->data;
}

// Display function
void display()
{
    struct Node *temp = front;

    if (temp == NULL)
    {
        printf("Queue is empty.\n");
        return;
    }

    printf("Queue elements (Front to Rear):\n");
    while (temp != NULL)
    {
        printf("%d\n", temp->data);
        temp = temp->next;
    }
}

int main()
{
    int n, value;

    printf("Enter number of elements to enqueue: ");
    scanf("%d", &n);

    for (int i = 0; i < n; i++)
    {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);
        enqueue(value);
    }

    display();

    int top = peek();
    if (top != -1)
        printf("Peek element (Front of Queue): %d\n", top);

    return 0;
}
```

Output:

<img width="823" height="383" alt="image" src="https://github.com/user-attachments/assets/eb1db59a-19cc-4f04-8b80-44026e8d2c6a" />

Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


