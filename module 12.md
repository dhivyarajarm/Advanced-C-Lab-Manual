

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

// 1. Define structure Node
struct Node {
    int data;
    struct Node *next;
};

// 2. Global variable head
struct Node *head = NULL;

// 3. Display function
void display()
{
    // 4. Declare pointer p and initialize with head
    struct Node *p = head;

    // 5. Traverse using while loop
    while (p != NULL)
    {
        // 6. Print data
        printf("%d ", p->data);

        // 7. Move to next node
        p = p->next;
    }
}

int main()
{
    // Creating nodes
    struct Node *n1, *n2, *n3;

    n1 = (struct Node *)malloc(sizeof(struct Node));
    n2 = (struct Node *)malloc(sizeof(struct Node));
    n3 = (struct Node *)malloc(sizeof(struct Node));

    // Assign data
    n1->data = 10;
    n2->data = 20;
    n3->data = 30;

    // Connect nodes
    n1->next = n2;
    n2->next = n3;
    n3->next = NULL;

    // Set head
    head = n1;

    // Display linked list
    display();

    return 0;
}
```

Output:

10 20 30


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

struct Node
{
    int data;
    struct Node *next;
};

struct Node *head = NULL;

// Push function to create stack
void push(int value)
{
    struct Node *newNode;

    newNode = (struct Node *)malloc(sizeof(struct Node));

    newNode->data = value;
    newNode->next = head;
    head = newNode;
}

// Pop function
void pop()
{
    // 1. Check for Empty Stack
    if (head == NULL)
    {
        // 2. If head is NULL
        printf("Stack is empty.\n");
    }
    else
    {
        // 4. Set head to next node
        struct Node *temp = head;

        printf("Deleted element: %d\n", head->data);

        head = head->next;

        free(temp);
    }
}

int main()
{
    push(10);
    push(20);
    push(30);

    printf("Stack before pop:\n");
    printf("30 20 10\n");

    pop();

    printf("Stack after pop:\n");

    if (head == NULL)
    {
        printf("Stack is empty.\n");
    }
    else
    {
        struct Node *p = head;

        while (p != NULL)
        {
            printf("%d ", p->data);
            p = p->next;
        }
    }

    return 0;
}
```

Output:

Stack before pop:
30 20 10
Deleted element: 30
Stack after pop:
20 10


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
void display()
{
    // 1. Check if Queue is Empty
    if (front == NULL)
    {
        printf("Queue is empty.\n");
    }
    else
    {
        // 2. Display Queue Elements
        struct Node *p = front;

        while (p != NULL)
        {
            // 3. Print data of current node
            printf("%d ", p->data);

            // 4. Update front/p to next node
            p = p->next;
        }
    }

    // 5. End display function
}
```

Output:

Queue elements:
10 20 30

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

struct Node
{
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void enqueue(int value)
{
    // 1. Allocate Memory for New Node
    struct Node *p;
    p = (struct Node *)malloc(sizeof(struct Node));

    // 2. Set Data and Next Pointer
    p->data = value;
    p->next = NULL;

    // 3. Check if Queue is Empty
    if (front == NULL)
    {
        // 4. Set both front and rear to new node
        front = p;
        rear = p;
    }
    else
    {
        // 5. Set current rear's next to new node
        rear->next = p;
        rear = p;
    }

    // 6. End of Enqueue Operation
}

int main()
{
    enqueue(10);
    enqueue(20);
    enqueue(30);

    printf("Queue elements: ");

    struct Node *temp = front;

    while (temp != NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }

    return 0;
}
```
Output:

Queue elements: 10 20 30

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

struct Node
{
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void enqueue(int value)
{
    struct Node *p = (struct Node *)malloc(sizeof(struct Node));

    p->data = value;
    p->next = NULL;

    if (front == NULL)
    {
        front = p;
        rear = p;
    }
    else
    {
        rear->next = p;
        rear = p;
    }
}

void peek()
{
    // Check if queue is empty
    if (front == NULL)
    {
        printf("Queue is empty.\n");
    }
    else
    {
        // Access front element
        printf("Front element: %d\n", front->data);
    }
}

int main()
{
    enqueue(10);
    enqueue(20);
    enqueue(30);

    peek();

    return 0;
}
```
Output:

Front element: 10



Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


