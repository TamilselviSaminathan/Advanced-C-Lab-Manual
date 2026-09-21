EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:




#include <stdio.h>
#include <stdlib.h>

struct Node
{
    char data;
    struct Node *next;
};

void search(struct Node *head, char key)
{
    int position = 1;

    while (head != NULL)
    {
        if (head->data == key)
        {
            printf("Element found at position %d\n", position);
            return;
        }

        head = head->next;
        position++;
    }

    printf("Element not found\n");
}

int main()
{
    struct Node *head = NULL;
    struct Node *newNode;
    struct Node *temp;
    char key;
    int n, i;

    scanf("%d", &n);

    for (i = 0; i < n; i++)
    {
        newNode = (struct Node *)malloc(sizeof(struct Node));

        scanf(" %c", &newNode->data);
        newNode->next = NULL;

        if (head == NULL)
        {
            head = newNode;
        }
        else
        {
            temp = head;

            while (temp->next != NULL)
            {
                temp = temp->next;
            }

            temp->next = newNode;
        }
    }

    scanf(" %c", &key);

    search(head, key);

    return 0;
}


Output:

<img width="355" height="302" alt="image" src="https://github.com/user-attachments/assets/a6f9c300-0f4f-485d-b0f3-52b3a6bb9c9c" />




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
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    char data;
    struct Node *next;
};

void insert(struct Node **head, char value)
{
    struct Node *newNode;
    struct Node *temp;

    newNode = (struct Node *)malloc(sizeof(struct Node));

    newNode->data = value;
    newNode->next = NULL;

    if (*head == NULL)
    {
        *head = newNode;
    }
    else
    {
        temp = *head;

        while (temp->next != NULL)
        {
            temp = temp->next;
        }

        temp->next = newNode;
    }
}

void display(struct Node *head)
{
    while (head != NULL)
    {
        printf("%c ", head->data);
        head = head->next;
    }
}

int main()
{
    struct Node *head = NULL;
    int n, i;
    char value;

    scanf("%d", &n);

    for (i = 0; i < n; i++)
    {
        scanf(" %c", &value);
        insert(&head, value);
    }

    printf("Linked List: ");
    display(head);

    return 0;
}


Output:

<img width="400" height="247" alt="image" src="https://github.com/user-attachments/assets/ec3f33ec-67b3-4e67-a41f-26f1185ce5d4" />


 
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

#include <stdio.h>
#include <stdlib.h>

struct Node
{
    char data;
    struct Node *prev;
    struct Node *next;
};

int main()
{
    struct Node *head = NULL;
    struct Node *temp;
    struct Node *newNode;
    int n, i;
    char value;

    scanf("%d", &n);

    for (i = 0; i < n; i++)
    {
        newNode = (struct Node *)malloc(sizeof(struct Node));

        scanf(" %c", &value);

        newNode->data = value;
        newNode->prev = NULL;
        newNode->next = NULL;

        if (head == NULL)
        {
            head = newNode;
        }
        else
        {
            temp = head;

            while (temp->next != NULL)
            {
                temp = temp->next;
            }

            temp->next = newNode;
            newNode->prev = temp;
        }
    }

    temp = head;

    while (temp != NULL)
    {
        printf("%c ", temp->data);
        temp = temp->next;
    }

    return 0;
}
Output:

<img width="192" height="257" alt="image" src="https://github.com/user-attachments/assets/e34d0521-2428-473e-9009-46bf22cdd87b" />



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
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    char data;
    struct Node *prev;
    struct Node *next;
};

void insert(struct Node **head, char value)
{
    struct Node *newNode;
    struct Node *temp;

    newNode = (struct Node *)malloc(sizeof(struct Node));

    newNode->data = value;
    newNode->prev = NULL;
    newNode->next = NULL;

    if (*head == NULL)
    {
        *head = newNode;
    }
    else
    {
        temp = *head;

        while (temp->next != NULL)
        {
            temp = temp->next;
        }

        temp->next = newNode;
        newNode->prev = temp;
    }
}

void display(struct Node *head)
{
    struct Node *temp = head;

    while (temp != NULL)
    {
        printf("%c ", temp->data);
        temp = temp->next;
    }
}

int main()
{
    struct Node *head = NULL;
    int n, i;
    char value;

    scanf("%d", &n);

    for (i = 0; i < n; i++)
    {
        scanf(" %c", &value);
        insert(&head, value);
    }

    printf("Doubly Linked List: ");
    display(head);

    return 0;
}


Output:

<img width="352" height="215" alt="image" src="https://github.com/user-attachments/assets/895e8fcf-c83d-4809-a020-0cf7954e804c" />



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
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    char data;
    struct Node *next;
};

void deleteElement(struct Node **head, char key)
{
    struct Node *temp;
    struct Node *prev;

    if (*head == NULL)
    {
        printf("List is empty\n");
        return;
    }

    temp = *head;

    if (temp->data == key)
    {
        *head = temp->next;
        free(temp);
        printf("Element deleted\n");
        return;
    }

    prev = NULL;

    while (temp != NULL && temp->data != key)
    {
        prev = temp;
        temp = temp->next;
    }

    if (temp == NULL)
    {
        printf("Element not found\n");
    }
    else
    {
        prev->next = temp->next;
        free(temp);
        printf("Element deleted\n");
    }
}

void display(struct Node *head)
{
    while (head != NULL)
    {
        printf("%c ", head->data);
        head = head->next;
    }
}

int main()
{
    struct Node *head = NULL;
    struct Node *newNode;
    struct Node *temp;
    int n, i;
    char value, key;

    scanf("%d", &n);

    for (i = 0; i < n; i++)
    {
        newNode = (struct Node *)malloc(sizeof(struct Node));

        scanf(" %c", &value);

        newNode->data = value;
        newNode->next = NULL;

        if (head == NULL)
        {
            head = newNode;
        }
        else
        {
            temp = head;

            while (temp->next != NULL)
            {
                temp = temp->next;
            }

            temp->next = newNode;
        }
    }

    scanf(" %c", &key);

    printf("Before deletion: ");
    display(head);

    deleteElement(&head, key);

    printf("\nAfter deletion: ");
    display(head);

    return 0;
}


Output:

<img width="551" height="332" alt="image" src="https://github.com/user-attachments/assets/29cc355b-0002-4f64-94be-af16eef41f60" />






Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





