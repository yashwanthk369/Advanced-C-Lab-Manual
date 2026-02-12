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

// Global variables
int stack[MAX];
int top = -1;

// Function to push element
void push(int value)
{
    if (top == MAX - 1)
    {
        printf("Stack Overflow\n");
        return;
    }
    top++;
    stack[top] = value;
    printf("%d pushed into stack\n", value);
}

// Function to pop element
void pop()
{
    if (top == -1)
    {
        printf("Stack Underflow\n");
        return;
    }
    printf("%d popped from stack\n", stack[top]);
    top--;
}

// Function to display stack elements
void display()
{
    int i;

    if (top == -1)
    {
        printf("Stack is Empty\n");
        return;
    }

    printf("Stack elements are:\n");
    for (i = top; i >= 0; i--)
    {
        printf("%d\n", stack[i]);
    }
}

int main()
{
    int choice, value;

    do
    {
        printf("\n1. Push\n2. Pop\n3. Display\n4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice)
        {
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
                printf("Exiting program.\n");
                break;

            default:
                printf("Invalid choice\n");
        }

    } while (choice != 4);

    return 0;
}
```

Output:

<img width="818" height="824" alt="image" src="https://github.com/user-attachments/assets/a4dbf2eb-c992-40c7-af09-2e2e642e6431" />

<img width="814" height="290" alt="image" src="https://github.com/user-attachments/assets/9a1b4381-88ef-43be-8066-f98aba4beb63" />

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

// Step 1: Global variables
float stack[MAX];
int top = -1;

// Step 2: Push function
void push(float value)
{
    if (top == MAX - 1)
    {
        printf("Stack Overflow. Cannot push %.2f\n", value);
        return;
    }

    top++;
    stack[top] = value;
    printf("%.2f pushed into stack successfully.\n", value);
}

int main()
{
    int n, i;
    float value;

    // Step 3: Initialization already done globally

    printf("Enter number of elements to push: ");
    scanf("%d", &n);

    // Step 4: Call push function
    for (i = 0; i < n; i++)
    {
        printf("Enter element %d: ", i + 1);
        scanf("%f", &value);
        push(value);
    }

    return 0;
}
```

Output:

<img width="813" height="355" alt="image" src="https://github.com/user-attachments/assets/384ea63c-1242-4ea6-89fa-90b08352c828" />

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

// Step 1: Global variables
int queue[MAX];
int front = -1;
int rear = -1;

// Function to insert element (Enqueue)
void enqueue(int value)
{
    if (rear == MAX - 1)
    {
        printf("Queue Overflow\n");
        return;
    }

    if (front == -1)
        front = 0;

    rear++;
    queue[rear] = value;
    printf("%d inserted into queue\n", value);
}

// Function to delete element (Dequeue)
void dequeue()
{
    if (front == -1 || front > rear)
    {
        printf("Queue Underflow\n");
        return;
    }

    printf("%d removed from queue\n", queue[front]);
    front++;

    if (front > rear)
    {
        front = rear = -1;  // Reset queue
    }
}

// Step 2: Display function
void display()
{
    int i;

    if (front == -1)
    {
        printf("Queue is Empty\n");
        return;
    }

    printf("Queue elements are:\n");
    for (i = front; i <= rear; i++)
    {
        printf("%d ", queue[i]);
    }
    printf("\n");
}

int main()
{
    int choice, value;

    do
    {
        printf("\n1. Enqueue\n2. Dequeue\n3. Display\n4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice)
        {
            case 1:
                printf("Enter value to insert: ");
                scanf("%d", &value);
                enqueue(value);
                break;

            case 2:
                dequeue();
                break;

            case 3:
                display();
                break;

            case 4:
                printf("Exiting program\n");
                break;

            default:
                printf("Invalid choice\n");
        }

    } while (choice != 4);

    return 0;
}
```

Output:

<img width="799" height="886" alt="image" src="https://github.com/user-attachments/assets/21f1ee96-0204-4bdf-b24f-4ebe8cafddd7" />

<img width="799" height="545" alt="image" src="https://github.com/user-attachments/assets/76c7e37c-ef8d-41f3-b725-b2f2b9dc8a15" />

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

// Step 1: Global variables
float queue[MAX];
int front = -1;
int rear = -1;

// Step 2: Enqueue function
void enqueue(float value)
{
    if (rear == MAX - 1)
    {
        printf("Queue Overflow. Cannot insert %.2f\n", value);
        return;
    }

    if (front == -1)
        front = 0;

    rear++;
    queue[rear] = value;

    printf("%.2f inserted into queue successfully.\n", value);
}

int main()
{
    int n, i;
    float value;

    // Step 3: Initialization already handled globally

    printf("Enter number of elements to insert: ");
    scanf("%d", &n);

    // Step 4: Call enqueue function
    for (i = 0; i < n; i++)
    {
        printf("Enter element %d: ", i + 1);
        scanf("%f", &value);
        enqueue(value);
    }

    return 0;
}
```

Output:

<img width="813" height="376" alt="image" src="https://github.com/user-attachments/assets/e073505d-dc62-4a9d-89f0-4d66fdcd159e" />


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

// Global variables
int queue[MAX];
int front = -1;
int rear = -1;

// Function to insert elements (for testing purpose)
void enqueue(int value)
{
    if (rear == MAX - 1)
    {
        printf("Queue Overflow\n");
        return;
    }

    if (front == -1)
        front = 0;

    queue[++rear] = value;
}

// EXP NO:15 - Delete function
void dequeue()
{
    // Step 1: Check if queue is empty
    if (front == -1)
    {
        printf("Queue is Empty. Cannot delete.\n");
        return;
    }

    // Step 2: Delete front element
    printf("%d deleted from queue\n", queue[front]);
    front++;

    // Step 3: Reset if queue becomes empty
    if (front > rear)
    {
        front = rear = -1;
    }
}

int main()
{
    int choice, value;

    do
    {
        printf("\n1. Enqueue\n2. Dequeue\n3. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice)
        {
            case 1:
                printf("Enter value to insert: ");
                scanf("%d", &value);
                enqueue(value);
                break;

            case 2:
                dequeue();
                break;

            case 3:
                printf("Exiting program\n");
                break;

            default:
                printf("Invalid choice\n");
        }

    } while (choice != 3);

    return 0;
}
```

Output:

<img width="812" height="758" alt="image" src="https://github.com/user-attachments/assets/5e573018-dcd6-468f-9ec0-3be8a58e0439" />


Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
