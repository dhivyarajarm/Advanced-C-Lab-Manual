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
    char data;
    struct Node *next;
};

int search(struct Node *head, char key) {
    while (head != NULL) {
        if (head->data == key)
            return 1;
        head = head->next;
    }
    return 0;
}

int main() {
    struct Node *head = NULL;
    struct Node *n1, *n2, *n3;
    char key;

    n1 = malloc(sizeof(struct Node));
    n2 = malloc(sizeof(struct Node));
    n3 = malloc(sizeof(struct Node));

    n1->data = 'A';
    n1->next = n2;

    n2->data = 'B';
    n2->next = n3;

    n3->data = 'C';
    n3->next = NULL;

    head = n1;

    scanf(" %c", &key);

    if (search(head, key))
        printf("Character found");
    else
        printf("Character not found");

    return 0;
}
```
Output:
Character found



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
    char data;
    struct Node *next;
};

void insert(struct Node **head, char ch) {
    struct Node *newNode;
    struct Node *temp;

    newNode = malloc(sizeof(struct Node));
    newNode->data = ch;
    newNode->next = NULL;

    if (*head == NULL) {
        *head = newNode;
    } else {
        temp = *head;

        while (temp->next != NULL)
            temp = temp->next;

        temp->next = newNode;
    }
}

void display(struct Node *head) {
    while (head != NULL) {
        printf("%c ", head->data);
        head = head->next;
    }
}

int main() {
    struct Node *head = NULL;
    int n, i;
    char ch;

    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        scanf(" %c", &ch);
        insert(&head, ch);
    }

    display(head);

    return 0;
}
```
Output:
A B C


 
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
    char data;
    struct Node *next;
};

int main() {
    struct Node *head, *temp;
    
    head = malloc(sizeof(struct Node));
    head->data = 'A';
    
    head->next = malloc(sizeof(struct Node));
    head->next->data = 'B';
    
    head->next->next = malloc(sizeof(struct Node));
    head->next->next->data = 'C';
    
    head->next->next->next = NULL;

    temp = head;

    while (temp != NULL) {
        printf("%c ", temp->data);
        temp = temp->next;
    }

    return 0;
}
```
Output:

A B C


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
    char data;
    struct Node *prev;
    struct Node *next;
};

void insert(struct Node **head, char value) {
    struct Node *newNode, *temp;

    newNode = malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->prev = NULL;
    newNode->next = NULL;

    if (*head == NULL) {
        *head = newNode;
    } else {
        temp = *head;

        while (temp->next != NULL)
            temp = temp->next;

        temp->next = newNode;
        newNode->prev = temp;
    }
}

void display(struct Node *head) {
    while (head != NULL) {
        printf("%c ", head->data);
        head = head->next;
    }
}

int main() {
    struct Node *head = NULL;

    insert(&head, 'A');
    insert(&head, 'B');
    insert(&head, 'C');

    display(head);

    return 0;
}
```
Output:
A B C



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

void deleteNode(struct Node **head, int value) {
    struct Node *temp = *head;
    struct Node *prev = NULL;

    if (*head == NULL) {
        printf("List is empty");
        return;
    }

    if (temp->data == value) {
        *head = temp->next;
        free(temp);
        return;
    }

    while (temp != NULL && temp->data != value) {
        prev = temp;
        temp = temp->next;
    }

    if (temp == NULL) {
        printf("Element not found");
        return;
    }

    prev->next = temp->next;
    free(temp);
}

void display(struct Node *head) {
    while (head != NULL) {
        printf("%d ", head->data);
        head = head->next;
    }
}

int main() {
    struct Node *head = NULL;
    struct Node *n1, *n2, *n3;
    int value;

    n1 = malloc(sizeof(struct Node));
    n2 = malloc(sizeof(struct Node));
    n3 = malloc(sizeof(struct Node));

    n1->data = 10;
    n1->next = n2;

    n2->data = 20;
    n2->next = n3;

    n3->data = 30;
    n3->next = NULL;

    head = n1;

    scanf("%d", &value);

    deleteNode(&head, value);

    display(head);

    return 0;
}
```
Output:

10 30




Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





