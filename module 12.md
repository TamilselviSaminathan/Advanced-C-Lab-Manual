

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

#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void push(int value)
{
    struct Node *newNode;

    newNode = (struct Node *)malloc(sizeof(struct Node));

    newNode->data = value;
    newNode->next = head;

    head = newNode;
}

void display()
{
    struct Node *p = head;

    if (p == NULL)
    {
        printf("Stack is empty");
        return;
    }

    printf("Stack elements:\n");

    while (p != NULL)
    {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main()
{
    push(10);
    push(20);
    push(30);
    push(40);

    display();

    return 0;
}

Output:

<img width="242" height="242" alt="image" src="https://github.com/user-attachments/assets/3442c576-6317-49c0-8f4c-b89cf64ddd6e" />



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

#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void push(int value)
{
    struct Node *newNode;

    newNode = (struct Node *)malloc(sizeof(struct Node));

    newNode->data = value;
    newNode->next = head;

    head = newNode;
}

void pop()
{
    struct Node *temp;

    if (head == NULL)
    {
        printf("Stack is empty\n");
    }
    else
    {
        temp = head;

        printf("Popped element: %d\n", head->data);

        head = head->next;

        free(temp);
    }
}

void display()
{
    struct Node *p = head;

    printf("Stack elements:\n");

    while (p != NULL)
    {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main()
{
    push(10);
    push(20);
    push(30);
    push(40);

    printf("Before pop:\n");
    display();

    pop();

    printf("After pop:\n");
    display();

    return 0;
}

Output:

<img width="302" height="362" alt="image" src="https://github.com/user-attachments/assets/58ad49cb-aa88-4242-b061-9734c3188416" />




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
    struct Node *newNode;

    newNode = (struct Node *)malloc(sizeof(struct Node));

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

void display()
{
    struct Node *temp;

    if (front == NULL)
    {
        printf("Queue is empty\n");
        return;
    }

    temp = front;

    printf("Queue elements:\n");

    while (temp != NULL)
    {
        printf("%d\n", temp->data);
        temp = temp->next;
    }
}

int main()
{
    enqueue(10);
    enqueue(20);
    enqueue(30);
    enqueue(40);

    display();

    return 0;
}

Output:

<img width="215" height="187" alt="image" src="https://github.com/user-attachments/assets/acbe6a64-a1a1-4420-89df-8bbfc4a42d11" />


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
    struct Node *p;

    p = (struct Node *)malloc(sizeof(struct Node));

    p->data = value;
    p->next = NULL;

    if (front == NULL)
    {
        front = rear = p;
    }
    else
    {
        rear->next = p;
        rear = p;
    }
}

void display()
{
    struct Node *temp = front;

    printf("Queue elements:\n");

    while (temp != NULL)
    {
        printf("%d\n", temp->data);
        temp = temp->next;
    }
}

int main()
{
    enqueue(10);
    enqueue(20);
    enqueue(30);
    enqueue(40);

    display();

    return 0;
}

Output:

<img width="200" height="220" alt="image" src="https://github.com/user-attachments/assets/53841333-4d7c-45d6-b19c-e086edcad015" />


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
    struct Node *newNode;

    newNode = (struct Node *)malloc(sizeof(struct Node));

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

void peek()
{
    if (front == NULL)
    {
        printf("Queue is empty\n");
    }
    else
    {
        printf("Peek element: %d\n", front->data);
    }
}

int main()
{
    enqueue(10);
    enqueue(20);
    enqueue(30);
    enqueue(40);

    peek();

    return 0;
}

Output:

<img width="422" height="156" alt="image" src="https://github.com/user-attachments/assets/44da06de-345f-4614-ad8c-ca9b9013644b" />




Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


