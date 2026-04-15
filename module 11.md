EXP NO:21

C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER

Aim:

To write a C program to create a function to find the greatest number

Algorithm:

1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
Program:

```

#include <stdio.h>
int max_of_four(int n1, int n2, int n3, int n4)
{
    int max;
    if (n1 >= n2 && n1 >= n3 && n1 >= n4)
        max = n1;
    else if (n2 >= n1 && n2 >= n3 && n2 >= n4)
        max = n2;
    else if (n3 >= n1 && n3 >= n2 && n3 >= n4)
        max = n3;
    else
        max = n4;
    return max;
}
int main()
{
    int n1, n2, n3, n4, greater;
    printf("Enter four integers: ");
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);
    greater = max_of_four(n1, n2, n3, n4);
    printf("Greatest number = %d\n", greater);
    return 0;
}

```


Output:

<img width="495" height="204" alt="image" src="https://github.com/user-attachments/assets/0d5c8609-465f-40f5-aa01-603b31394f89" />


Result:

Thus, the program  that create a function to find the greatest number is verified successfully.


 
EXP NO:22 

C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS

Aim:

To write a C program to print the maximum values for the AND, OR and XOR comparisons

Algorithm:

1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
Program:

```

#include <stdio.h>
void calculate_the_max(int n, int k)
{
    int a = 0, o = 0, x = 0;
    for (int i = 1; i <= n; i++)
    {
        for (int j = i + 1; j <= n; j++)
        {
            if ((i & j) < k && (i & j) > a)
                a = i & j;
            if ((i | j) < k && (i | j) > o)
                o = i | j;
            if ((i ^ j) < k && (i ^ j) > x)
                x = i ^ j;
        }
    }
    printf("Maximum AND value = %d\n", a);
    printf("Maximum OR value  = %d\n", o);
    printf("Maximum XOR value = %d\n", x);
}
int main()
{
    int n, k;
    printf("Enter values of n and k: ");
    scanf("%d %d", &n, &k);
    calculate_the_max(n, k);
    return 0;
}

```

Output:

<img width="597" height="254" alt="image" src="https://github.com/user-attachments/assets/d9c32b6a-761c-4d06-82b4-186eaa1fefa8" />



Result:


Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
EXP NO:23 

C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS

Aim:

To write a C program to write the logic for the requests

Algorithm:

1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
Program:

```

#include <stdio.h>
#include <stdlib.h>
int main()
{
    int noshel, noque;
    scanf("%d %d", &noshel, &noque);
    int *nobookarr = (int *)calloc(noshel, sizeof(int));
    int **shelarr = (int **)malloc(noshel * sizeof(int *));
    int type, x, y;
    for (int i = 0; i < noque; i++)
    {
        scanf("%d", &type);
        if (type == 1)
        {
            scanf("%d %d", &x, &y);
            nobookarr[x]++; 
            shelarr[x] = (int *)realloc(shelarr[x], nobookarr[x] * sizeof(int));
            shelarr[x][nobookarr[x] - 1] = y;
        }
        else if (type == 2)
        {
            scanf("%d %d", &x, &y);
            printf("%d\n", shelarr[x][y]);
        }
        else if (type == 3)
        {
            scanf("%d", &x);
            printf("%d\n", nobookarr[x]);
        }
    }
    for (int i = 0; i < noshel; i++)
    {
        free(shelarr[i]);
    }
    free(shelarr);
    free(nobookarr);
    return 0;
}

```

Output:

<img width="571" height="281" alt="image" src="https://github.com/user-attachments/assets/1af251cf-f699-4bbc-8926-745db1ad6f81" />



Result:

Thus, the program to write the logic for the requests is verified successfully.


 
EXP NO:24 

C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.

Aim:

To write a C program print the sum of the integers in the array.

Algorithm:

1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



Program:

```

#include <stdio.h>
int main()
{
    int n;
    scanf("%d", &n);
    int a[n];  
    int sum = 0;
    for (int i = 0; i < n; i++)
    {
        scanf("%d", &a[i]);
        sum += a[i];
    }
    printf("Sum = %d\n", sum);
    return 0;
}

```

Output:

<img width="594" height="227" alt="image" src="https://github.com/user-attachments/assets/bfd8e2fe-4713-42cf-a758-bda208f28a80" />


Result:

Thus, the program prints the sum of the integers in the array is verified successfully.


 
EXP NO 25: 

C PROGRAM TO COUNT THE NUMBER OF WORDS IN A      SENTENCE

Aim:

To write a C program that counts the number of words in a given sentence.

Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



Program:

```

#include <stdio.h>
int main()
{
    char str[200];
    int i = 0, count = 0;
    printf("Enter a sentence: ");
    fgets(str, sizeof(str), stdin);
    while (str[i] != '\0')
    {
        if ((str[i] != ' ' && str[i] != '\n') &&
            (i == 0 || str[i - 1] == ' '))
        {
            count++;
        }
        i++;
    }
    printf("Number of words = %d\n", count);
    return 0;
}

```


Output:

<img width="542" height="223" alt="image" src="https://github.com/user-attachments/assets/6a248c2c-8abf-4033-9f15-857fc50646d5" />


Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
