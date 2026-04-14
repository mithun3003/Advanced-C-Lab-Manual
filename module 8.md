EXP NO:6

C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER

Aim:

To write a C program print the lowercase English word corresponding to the number

Algorithm:

1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:

```

#include <stdio.h>
int main() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);
    switch(n) {
        case 1: printf("one"); break;
        case 2: printf("two"); break;
        case 3: printf("three"); break;
        case 4: printf("four"); break;
        case 5: printf("five"); break;
        case 6: printf("six"); break;
        case 7: printf("seven"); break;
        case 8: printf("eight"); break;
        case 9: printf("nine"); break;
        case 10: printf("ten"); break;
        case 11: printf("eleven"); break;
        case 12: printf("twelve"); break;
        case 13: printf("thirteen"); break;
        default:
            printf("Greater than 13");
    }
    return 0;
}

```

Output:

<img width="489" height="166" alt="image" src="https://github.com/user-attachments/assets/7f07d313-617a-4914-b564-fca1d2a6c085" />


Result:

Thus, the program is verified successfully

 
EXP NO:7 

C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .

Aim:

To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.

Algorithm:

1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:

```

#include <stdio.h>
int main() {
    char a[50];
    int i, digit, count;
    printf("Enter a number/string: ");
    scanf("%s", a);
    for (digit = 0; digit <= 3; digit++) {
        count = 0;
        for (i = 0; a[i] != '\0'; i++) {
            if (a[i] == digit + '0') {
                count++;
            }
        }
        printf("%d ", count);
    }
    return 0;
}

```

Output:

<img width="504" height="154" alt="image" src="https://github.com/user-attachments/assets/0ab2e130-4f3e-438b-a0a5-2846fa6791d8" />


Result:

Thus, the program is verified successfully


EXP NO:8 

C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.

Aim:

To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:

1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)
3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:

```

#include <stdio.h>
#include <stdlib.h>
#include <string.h>
int compare(const void *a, const void *b) {
    return strcmp(*(const char **)a, *(const char **)b);
}
void swap(char **a, char **b) {
    char *temp = *a;
    *a = *b;
    *b = temp;
}
int next_permutation(char **s, int n) {
    int i = n - 2;
    while (i >= 0 && strcmp(s[i], s[i + 1]) >= 0)
        i--;
    if (i < 0)
        return 0;
    int j = n - 1;
    while (strcmp(s[j], s[i]) <= 0)
        j--;
    swap(&s[i], &s[j]);
    int left = i + 1, right = n - 1;
    while (left < right) {
        swap(&s[left], &s[right]);
        left++;
        right--;
    }
    return 1;
}
int main() {
    char **s;
    int n, i;
    printf("Enter number of strings: ");
    scanf("%d", &n);
    s = (char **)malloc(n * sizeof(char *));
    for (i = 0; i < n; i++) {
        s[i] = (char *)malloc(50 * sizeof(char));
    }
    printf("Enter strings:\n");
    for (i = 0; i < n; i++) {
        scanf("%s", s[i]);
    }
    qsort(s, n, sizeof(char *), compare);
    do {
        for (i = 0; i < n; i++) {
            printf("%s ", s[i]);
        }
        printf("\n");
    } while (next_permutation(s, n));
    for (i = 0; i < n; i++) {
        free(s[i]);
    }
    free(s);
    return 0;
}

```

Output:

<img width="570" height="251" alt="image" src="https://github.com/user-attachments/assets/dd523672-63e0-4447-9c75-a37e650da0ed" />


Result:
Thus, the program is verified successfully

 
EXP NO:9

C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.

Aim:

To write a C program to print a pattern of numbers from 1 to n as shown below.

Algorithm:

1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:

```

#include <stdio.h>
int main() {
    int n, i, j, min, len;
    printf("Enter n: ");
    scanf("%d", &n);
    len = 2 * n - 1;
    for (i = 0; i < len; i++) {
        for (j = 0; j < len; j++) {
            int top = i;
            int left = j;
            int right = len - j - 1;
            int bottom = len - i - 1;
            min = top;
            if (left < min) min = left;
            if (right < min) min = right;
            if (bottom < min) min = bottom;
            printf("%d ", n - min);
        }
        printf("\n");
    }
    return 0;
}

```

Output:

<img width="549" height="456" alt="image" src="https://github.com/user-attachments/assets/7d7084b1-fb79-41fb-9af8-99c564cbd175" />


Result:

Thus, the program is verified successfully


EXP NO:10

C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:

```

#include <stdio.h>
int square() {
    int num, result;
    printf("Enter a number: ");
    scanf("%d", &num);
    result = num * num;
    return result;
}
int main() {
    int res;
    res = square();
    printf("Square = %d\n", res);
    return 0;
}

```

Output:

<img width="494" height="179" alt="image" src="https://github.com/user-attachments/assets/86e75150-b878-4a6a-96e0-fdddd9a6b171" />


Result:

Thus, the program is verified successfully
