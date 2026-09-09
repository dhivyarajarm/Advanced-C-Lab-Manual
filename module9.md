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

int stack[100], top = -1;

void push(int value) {
    stack[++top] = value;
}

void pop() {
    if (top == -1)
        printf("Stack is empty\n");
    else
        top--;
}

void display() {
    int i;

    if (top == -1) {
        printf("Stack is empty");
        return;
    }

    for (i = top; i >= 0; i--)
        printf("%d ", stack[i]);
}

int main() {
    push(10);
    push(20);
    push(30);

    printf("Stack: ");
    display();

    printf("\nAfter pop: ");
    pop();
    display();

    return 0;
}
```
Output:
Stack: 30 20 10
After pop: 20 10




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

#define SIZE 100

float stack[SIZE];
int top = -1;

void push(float value) {
    if (top == SIZE - 1)
        printf("Stack Overflow\n");
    else
        stack[++top] = value;
}

int main() {
    push(10.5);
    push(20.5);
    push(30.5);

    printf("Stack elements:\n");

    for (int i = top; i >= 0; i--)
        printf("%.1f\n", stack[i]);

    return 0;
}
```
Output:
Stack elements:
30.5
20.5
10.5





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

#define SIZE 100

int queue[SIZE];
int front = 0, rear = -1;

void display() {
    int i;

    if (rear < front) {
        printf("Queue is empty");
        return;
    }

    for (i = front; i <= rear; i++)
        printf("%d ", queue[i]);
}

int main() {
    queue[++rear] = 10;
    queue[++rear] = 20;
    queue[++rear] = 30;

    printf("Queue elements: ");
    display();

    return 0;
}
```


Output:

Queue elements: 10 20 30


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

#define SIZE 100

float queue[SIZE];
int front = 0, rear = -1;

void enqueue(float value) {
    if (rear == SIZE - 1)
        printf("Queue is full\n");
    else
        queue[++rear] = value;
}

int main() {
    enqueue(10.5);
    enqueue(20.5);
    enqueue(30.5);

    printf("Queue elements:\n");

    for (int i = front; i <= rear; i++)
        printf("%.1f ", queue[i]);

    return 0;
}
```

Output:
Queue elements:
10.5 20.5 30.5


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

#define SIZE 100

int queue[SIZE];
int front = -1, rear = -1;

void dequeue() {
    if (front == -1) {
        printf("Queue is empty\n");
        return;
    }

    printf("Deleted: %d\n", queue[front]);
    front++;

    if (front > rear) {
        front = -1;
        rear = -1;
    }
}

int main() {
    queue[++rear] = 10;
    front = 0;
    queue[++rear] = 20;
    queue[++rear] = 30;

    dequeue();

    printf("Queue after deletion: ");

    if (front == -1) {
        printf("Queue is empty");
    } else {
        for (int i = front; i <= rear; i++)
            printf("%d ", queue[i]);
    }

    return 0;
}
```

Output:

Deleted: 10
Queue after deletion: 20 30


Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
