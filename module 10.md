EXP NO:16 

C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.

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
struct node {
    char data;
    struct node* next;
};
struct node* createNode(char value) {
    struct node* newNode = (struct node*)malloc(sizeof(struct node));
    newNode->data = value;
    newNode->next = NULL;
    return newNode;
}
void search(struct node* head, char key) {
    struct node* temp = head;
    int position = 1;
    while (temp != NULL) {
        if (temp->data == key) {
            printf("Element '%c' found at position %d\n", key, position);
            return;
        }
        temp = temp->next;
        position++;
    }
    printf("Element '%c' not found in the list\n", key);
}
int main() {
    struct node* head = NULL;
    struct node* second = NULL;
    struct node* third = NULL;
    head = createNode('A');
    second = createNode('B');
    third = createNode('C');
    head->next = second;
    second->next = third;
    char key;
    printf("Enter character to search: ");
    scanf(" %c", &key);
    search(head, key);
    return 0;
}

```

Output:

<img width="498" height="223" alt="image" src="https://github.com/user-attachments/assets/b588ee8d-6248-4075-923b-e723346706ca" />


Result:

Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  

PROGRAM TO INSERT A NODE IN A LINKED LIST.

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
struct node {
    char data;
    struct node* next;
};
struct node* createNode(char value) {
    struct node* newNode = (struct node*)malloc(sizeof(struct node));
    newNode->data = value;
    newNode->next = NULL;
    return newNode;
}
struct node* insert(struct node* head, char value) {
    struct node* newNode = createNode(value);
    if (head == NULL) {
        return newNode;
    }
    struct node* temp = head;
    while (temp->next != NULL) {
        temp = temp->next;
    }
    temp->next = newNode;
    return head;
}
void display(struct node* head) {
    struct node* temp = head;
    while (temp != NULL) {
        printf("%c -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}
int main() {
    struct node* head = NULL;
    head = insert(head, 'A');
    head = insert(head, 'B');
    head = insert(head, 'C');
    printf("Linked List:\n");
    display(head);
    return 0;
}

```

Output:

<img width="506" height="229" alt="image" src="https://github.com/user-attachments/assets/8dd7a7f0-28c3-4f6e-a9ab-ae4ce9a85a8f" />



Result:

Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 

C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST

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
struct node {
    int data;
    struct node* prev;
    struct node* next;
};
struct node* createNode(int value) {
    struct node* newNode = (struct node*)malloc(sizeof(struct node));
    newNode->data = value;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}
void traverse(struct node* head) {
    struct node* temp = head;
    while (temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}
int main() {
    struct node* head = createNode(10);
    struct node* second = createNode(20);
    struct node* third = createNode(30);
    head->next = second;
    second->prev = head;
    second->next = third;
    third->prev = second;
    printf("Doubly Linked List:\n");
    traverse(head);
    return 0;
}

```

Output:

<img width="505" height="178" alt="image" src="https://github.com/user-attachments/assets/a90cb23a-534f-4084-bf03-b5ca50c57f31" />


Result:

Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 

C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST

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
struct node {
    int data;
    struct node* prev;
    struct node* next;
};
struct node* insert(struct node* head, int value) {
    struct node* newNode = (struct node*)malloc(sizeof(struct node));
    newNode->data = value;
    newNode->next = NULL;
    if (head == NULL) {
        newNode->prev = NULL;
        return newNode;
    }
    struct node* temp = head;
    while (temp->next != NULL) {
        temp = temp->next;
    }
    temp->next = newNode;
    newNode->prev = temp;
    return head;
}
void display(struct node* head) {
    struct node* temp = head;
    while (temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}
int main() {
    struct node* head = NULL;
    head = insert(head, 10);
    head = insert(head, 20);
    head = insert(head, 30);
    printf("Doubly Linked List:\n");
    display(head);
    return 0;
}

```

Output:

<img width="504" height="180" alt="image" src="https://github.com/user-attachments/assets/54bdc74f-f355-4558-9dbc-7fbd2f08e8a4" />


Result:

Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 

C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST

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
struct node {
    int data;
    struct node* next;
};
struct node* insert(struct node* head, int value) {
    struct node* newNode = (struct node*)malloc(sizeof(struct node));
    newNode->data = value;
    newNode->next = NULL;
    if (head == NULL)
        return newNode;
    struct node* temp = head;
    while (temp->next != NULL)
        temp = temp->next;
    temp->next = newNode;
    return head;
}
void display(struct node* head) {
    if (head == NULL) {
        printf("List is empty\n");
        return;
    }
    while (head != NULL) {
        printf("%d -> ", head->data);
        head = head->next;
    }
    printf("NULL\n");
}
struct node* deleteElement(struct node* head, int key) {
    if (head == NULL) {
        printf("List is empty\n");
        return head;
    }
    struct node *temp = head, *prev = NULL;
    if (temp->data == key) {
        head = temp->next;
        free(temp);
        printf("Element %d deleted\n", key);
        return head;
    }
    while (temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }
    if (temp == NULL) {
        printf("Element not found\n");
        return head;
    }
    prev->next = temp->next;
    free(temp);
    printf("Element %d deleted\n", key);
    return head;
}
int main() {
    struct node* head = NULL;
    int value, key, n, i;
    printf("Enter number of elements: ");
    scanf("%d", &n);
    for (i = 0; i < n; i++) {
        printf("Enter value: ");
        scanf("%d", &value);
        head = insert(head, value);
    }
    printf("\nLinked List:\n");
    display(head);
    printf("\nEnter element to delete: ");
    scanf("%d", &key);
    head = deleteElement(head, key);
    printf("\nUpdated Linked List:\n");
    display(head);
    return 0;
}

```

Output:

<img width="551" height="599" alt="image" src="https://github.com/user-attachments/assets/9b8509b1-a56c-4722-a331-ea12c2867ec7" />

Result:

Thus, the function that deletes a given element from a linked list is verified successfully.
