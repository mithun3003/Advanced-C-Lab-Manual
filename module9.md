EXP NO:11

C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

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
int stack[MAX];
int top = -1;
void push(int value) {
    if (top == MAX - 1) {
        printf("Stack Overflow\n");
    } else {
        top++;
        stack[top] = value;
        printf("%d pushed into stack\n", value);
    }
}
void pop() {
    if (top == -1) {
        printf("Stack Underflow\n");
    } else {
        printf("%d popped from stack\n", stack[top]);
        top--;
    }
}
void display() {
    if (top == -1) {
        printf("Stack is empty\n");
    } else {
        printf("Stack elements are:\n");
        for (int i = top; i >= 0; i--) {
            printf("%d\n", stack[i]);
        }
    }
}
int main() {
    int choice, value;
    while (1) {
        printf("\n1. Push\n2. Pop\n3. Display\n4. Exit\n");
        printf("Enter your choice: ");
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
                printf("Invalid choice\n");
        }
    }
    return 0;
}

```

Output:

<img width="320" height="522" alt="image" src="https://github.com/user-attachments/assets/f77056e1-5050-4ce3-b791-d0aada5b9914" />


Result:

Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  

PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.

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
float stack[MAX];
int top = -1;
void push(float value) {
    if (top == MAX - 1) {
        printf("Stack Overflow\n");
    } else {
        top++;
        stack[top] = value;
        printf("Element %.2f pushed into stack\n", value);
    }
}
int main() {
    float value;
    printf("Enter a floating-point value to push: ");
    scanf("%f", &value);
    push(value);
    return 0;
}

```

Output:

<img width="605" height="177" alt="image" src="https://github.com/user-attachments/assets/089bd9c6-c9fe-40e7-9ced-1f3580a96ec4" />


Result:

Thus, the program to push the given element in to a stack using array is verified successfully


 
EXP NO:13

C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.

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
int queue[MAX];
int front = -1, rear = -1;
int i;
void enqueue(int value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow\n");
    } else {
        if (front == -1)
            front = 0;
        rear++;
        queue[rear] = value;
        printf("%d inserted into queue\n", value);
    }
}
void display() {
    if (front == -1 || front > rear) {
        printf("Queue is empty\n");
    } else {
        printf("Queue elements are:\n");
        for (i = front; i <= rear; i++) {
            printf("%d\n", queue[i]);
        }
    }
}
int main() {
    int choice, value;
    while (1) {
        printf("\n1. Enqueue\n2. Display\n3. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
        switch (choice) {
            case 1:
                printf("Enter value to insert: ");
                scanf("%d", &value);
                enqueue(value);
                break;
            case 2:
                display();
                break;
            case 3:
                return 0;
            default:
                printf("Invalid choice\n");
        }
    }
    return 0;
}

```

Output:

<img width="570" height="654" alt="image" src="https://github.com/user-attachments/assets/a05f6b7e-b7cf-4991-8d9d-61fc735c7cdf" />




Result:

Thus, the program to display queue elements using array is verified successfully.



 
EXP NO:14 

C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.

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
float queue[MAX];
int front = -1, rear = -1
void enqueue(float value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow\n");
    } else {
        if (front == -1)
            front = 0;
        rear++;
        queue[rear] = value;
        printf("Element %.2f inserted into queue\n", value);
    }
}
int main() {
    float value;
    printf("Enter a floating-point value to insert into queue: ");
    scanf("%f", &value);
    enqueue(value);
    return 0;
}

```

Output:

<img width="739" height="174" alt="image" src="https://github.com/user-attachments/assets/d800cda8-45d4-4d58-90e6-5af1b1168c4f" />



Result:

Thus, the program to insert elements in queue using array is verified successfully.



 
EXP NO:15 

C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY

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
int queue[MAX];
int front = -1, rear = -1;
void dequeue() {
    if (front == -1) {
        printf("Queue is empty\n");
        return;
    }
    printf("Deleted element: %d\n", queue[front]);
    front++;
    if (front > rear) {
        front = rear = -1;
    }
}
int main() {
    dequeue();  // function call
    return 0;
}

```

Output:

<img width="635" height="149" alt="image" src="https://github.com/user-attachments/assets/1c01b3f8-8cfb-40ff-8022-889257616753" />


Result:

Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
