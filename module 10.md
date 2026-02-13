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

// Step 1: Define structure
struct Node
{
    int data;
    struct Node *next;
};

// Function to insert at end (for building list)
struct Node* insert(struct Node *head, int value)
{
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;

    if (head == NULL)
        return newNode;

    struct Node *temp = head;
    while (temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
    return head;
}

// Step 2: Search function
void search(struct Node *head, int key)
{
    int position = 1;
    struct Node *temp = head;

    while (temp != NULL)
    {
        if (temp->data == key)
        {
            printf("Element %d found at position %d\n", key, position);
            return;
        }
        temp = temp->next;
        position++;
    }

    printf("Element %d not found in the list\n", key);
}

int main()
{
    struct Node *head = NULL;
    int n, i, value, key;

    // Step 3: Initialize linked list
    printf("Enter number of elements: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++)
    {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);
        head = insert(head, value);
    }

    // Step 4: Search operation
    printf("Enter element to search: ");
    scanf("%d", &key);

    search(head, key);

    return 0;
}
```

Output:

<img width="808" height="365" alt="image" src="https://github.com/user-attachments/assets/eeebf207-e956-49ff-83a8-8bc0ee565d9f" />


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

// Step 1: Define structure
struct Node
{
    char data;
    struct Node *next;
};

// Step 2: Insert function (at end)
struct Node* insert(struct Node *head, char value)
{
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));

    if (newNode == NULL)
    {
        printf("Memory allocation failed.\n");
        return head;
    }

    newNode->data = value;
    newNode->next = NULL;

    if (head == NULL)
        return newNode;

    struct Node *temp = head;
    while (temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
    return head;
}

// Function to display linked list
void display(struct Node *head)
{
    struct Node *temp = head;

    if (head == NULL)
    {
        printf("Linked list is empty.\n");
        return;
    }

    printf("Linked List Elements: ");
    while (temp != NULL)
    {
        printf("%c -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main()
{
    struct Node *head = NULL;
    int n, i;
    char value;

    // Step 3: Initialize list
    printf("Enter number of nodes: ");
    scanf("%d", &n);

    // Step 4: Insert nodes
    for (i = 0; i < n; i++)
    {
        printf("Enter character for node %d: ", i + 1);
        scanf(" %c", &value);  // Space before %c to clear buffer
        head = insert(head, value);
    }

    // Display list
    display(head);

    return 0;
}
```


Output:

<img width="806" height="332" alt="image" src="https://github.com/user-attachments/assets/c240ac52-f4eb-4995-bd40-0e0f91b5ff3e" />
 
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

// Define structure for doubly linked list node
struct Node
{
    int data;
    struct Node *prev;
    struct Node *next;
};

// Function to insert node at end (for building list)
struct Node* insert(struct Node *head, int value)
{
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));

    if (newNode == NULL)
    {
        printf("Memory allocation failed.\n");
        return head;
    }

    newNode->data = value;
    newNode->prev = NULL;
    newNode->next = NULL;

    if (head == NULL)
        return newNode;

    struct Node *temp = head;

    while (temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
    newNode->prev = temp;

    return head;
}

// Traversal function
void traverse(struct Node *head)
{
    // Step 1: Initialize temp pointer
    struct Node *temp = head;

    // Step 2: Traverse until temp == NULL
    while (temp != NULL)
    {
        // Step 3: Print data
        printf("%d <-> ", temp->data);

        // Step 4: Move to next node
        temp = temp->next;
    }

    printf("NULL\n");
}

int main()
{
    struct Node *head = NULL;
    int n, i, value;

    printf("Enter number of nodes: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++)
    {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);
        head = insert(head, value);
    }

    printf("\nDoubly Linked List Traversal:\n");
    traverse(head);

    return 0;
}
```

Output:

<img width="811" height="375" alt="image" src="https://github.com/user-attachments/assets/ce87658e-7854-454b-b189-225b0f8cad00" />

Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, s
4.Let the new node as the head.
10.	If the list is not empty, traverse the list to find the last node.
11.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

// Define structure for doubly linked list
struct Node
{
    int data;
    struct Node *prev;
    struct Node *next;
};

// Insert at end function
struct Node* insert(struct Node *head, int value)
{
    // Step 1: Create new node
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));

    if (newNode == NULL)
    {
        printf("Memory allocation failed.\n");
        return head;
    }

    // Step 2: Assign data
    newNode->data = value;
    newNode->prev = NULL;
    newNode->next = NULL;

    // Step 3: If list is empty
    if (head == NULL)
        return newNode;

    // Step 4: Traverse to last node
    struct Node *temp = head;
    while (temp->next != NULL)
        temp = temp->next;

    // Step 5: Update pointers
    temp->next = newNode;
    newNode->prev = temp;

    return head;
}

// Display function
void display(struct Node *head)
{
    struct Node *temp = head;

    if (head == NULL)
    {
        printf("List is empty.\n");
        return;
    }

    printf("Doubly Linked List: ");
    while (temp != NULL)
    {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main()
{
    struct Node *head = NULL;
    int n, i, value;

    printf("Enter number of nodes: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++)
    {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);
        head = insert(head, value);
    }

    display(head);

    return 0;
}
```

Output:

<img width="825" height="335" alt="image" src="https://github.com/user-attachments/assets/370fe125-de33-49e2-a705-dd9a20bef5a1" />


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

// Define structure for singly linked list
struct Node
{
    int data;
    struct Node *next;
};

// Insert at end (for building list)
struct Node* insert(struct Node *head, int value)
{
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));

    if (newNode == NULL)
    {
        printf("Memory allocation failed.\n");
        return head;
    }

    newNode->data = value;
    newNode->next = NULL;

    if (head == NULL)
        return newNode;

    struct Node *temp = head;
    while (temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
    return head;
}

// Function to delete given element
struct Node* deleteElement(struct Node *head, int key)
{
    // Step 1: Check if list is empty
    if (head == NULL)
    {
        printf("Linked list is empty.\n");
        return head;
    }

    struct Node *temp = head;
    struct Node *prev = NULL;

    // Step 3: If element is in first node
    if (temp->data == key)
    {
        head = temp->next;
        free(temp);
        printf("Element %d deleted successfully.\n", key);
        return head;
    }

    // Step 2 & 4: Traverse list
    while (temp != NULL && temp->data != key)
    {
        prev = temp;
        temp = temp->next;
    }

    // Step 5: If element not found
    if (temp == NULL)
    {
        printf("Element %d not found in the list.\n", key);
        return head;
    }

    // Delete middle or last node
    prev->next = temp->next;
    free(temp);

    printf("Element %d deleted successfully.\n", key);
    return head;
}

// Display function
void display(struct Node *head)
{
    struct Node *temp = head;

    if (head == NULL)
    {
        printf("List is empty.\n");
        return;
    }

    printf("Linked List: ");
    while (temp != NULL)
    {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main()
{
    struct Node *head = NULL;
    int n, i, value, key;

    printf("Enter number of nodes: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++)
    {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &value);
        head = insert(head, value);
    }

    display(head);

    printf("Enter element to delete: ");
    scanf("%d", &key);

    head = deleteElement(head, key);

    display(head);

    return 0;
}
```

Output:

<img width="807" height="377" alt="image" src="https://github.com/user-attachments/assets/37fad0b0-e1c2-47fd-bb5a-a8724faeae9a" />

Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





