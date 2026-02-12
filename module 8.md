Name : YASHWANTH K

Reg No : 21222404369

EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
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

int main()
{
    int n;

    // Step 2: Input
    printf("Enter a number (5 to 13): ");
    scanf("%d", &n);

    // Step 3: Switch cases
    switch(n)
    {
        case 5:
            printf("seventy one\n");
            break;

        case 6:
            printf("seventy two\n");
            break;

        case 7:
            printf("seventy three\n");
            break;

        case 8:
            printf("seventy four\n");
            break;

        case 9:
            printf("seventy five\n");
            break;

        case 10:
            printf("seventy six\n");
            break;

        case 11:
            printf("seventy seven\n");
            break;

        case 12:
            printf("seventy eight\n");
            break;

        case 13:
            printf("seventy nine\n");
            break;

        default:
            printf("Greater than 13 or lesser than 5\n");
    }

    return 0;
}
```




Output:


<img width="816" height="256" alt="image" src="https://github.com/user-attachments/assets/2fea22ba-473b-4421-babf-fd9827e31bc3" />

<img width="822" height="250" alt="image" src="https://github.com/user-attachments/assets/c11f6d11-3721-4a3d-bf24-e01e31311927" />



Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
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
#include <string.h>

int main()
{
    char a[50];
    int i, digit, c;

    // Step 2: Input string
    printf("Enter a number: ");
    scanf("%s", a);

    // Outer loop for digits 0 to 3
    for (digit = 0; digit <= 3; digit++)
    {
        c = 0;   // Step 3: Initialize counter

        // Count frequency of current digit
        for (i = 0; i < strlen(a); i++)
        {
            if (a[i] == digit + '0')
            {
                c++;
            }
        }

        // Step 4: Print count followed by space
        printf("%d ", c);
    }

    return 0;
}

```



Output:


<img width="818" height="219" alt="image" src="https://github.com/user-attachments/assets/65cc71a1-8b6e-4c3f-bd54-1f082bf5eb01" />

<img width="835" height="231" alt="image" src="https://github.com/user-attachments/assets/348f61ca-ae42-4fc0-bbb6-483300ad51de" />

<img width="824" height="245" alt="image" src="https://github.com/user-attachments/assets/909b2b1f-07f3-476a-9920-26d061cea6a4" />

Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
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

// Comparator for qsort
int compare(const void *a, const void *b)
{
    return strcmp(*(const char **)a, *(const char **)b);
}

// Function to swap strings
void swap(char **a, char **b)
{
    char *temp = *a;
    *a = *b;
    *b = temp;
}

// Function to generate permutations
void permute(char **s, int l, int r)
{
    int i;

    if (l == r)
    {
        for (i = 0; i <= r; i++)
            printf("%s ", s[i]);
        printf("\n");
        return;
    }

    for (i = l; i <= r; i++)
    {
        swap(&s[l], &s[i]);
        permute(s, l + 1, r);
        swap(&s[l], &s[i]); // backtrack
    }
}

int main()
{
    int n, i;

    printf("Enter number of strings: ");
    scanf("%d", &n);

    // Step 3: Allocate memory for array of string pointers
    char **s = (char **)malloc(n * sizeof(char *));

    if (s == NULL)
    {
        printf("Memory allocation failed.\n");
        return 1;
    }

    // Step 4: Allocate memory for each string
    for (i = 0; i < n; i++)
    {
        s[i] = (char *)malloc(50 * sizeof(char));

        if (s[i] == NULL)
        {
            printf("Memory allocation failed.\n");
            return 1;
        }

        printf("Enter string %d: ", i + 1);
        scanf("%s", s[i]);
    }

    // Sort strings for lexicographical order
    qsort(s, n, sizeof(char *), compare);

    printf("\nPermutations in lexicographical order:\n");
    permute(s, 0, n - 1);

    // Step 6: Free memory
    for (i = 0; i < n; i++)
        free(s[i]);

    free(s);

    return 0;
}
```




Output:

<img width="821" height="481" alt="image" src="https://github.com/user-attachments/assets/a9f0f68e-4142-4cf5-bd22-2bf45d8a23c1" />

<img width="806" height="346" alt="image" src="https://github.com/user-attachments/assets/286be8df-de0f-46f6-b7b6-531adc7c219c" />


Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
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

int main()
{
    int n, i, j, min;
    
    // Step 3: Read n
    printf("Enter the value of n: ");
    scanf("%d", &n);

    // Step 4: Calculate length
    int len = 2 * n - 1;

    // Step 5: Matrix generation loop
    for (i = 0; i < len; i++)
    {
        for (j = 0; j < len; j++)
        {
            // Step 6: Calculate minimum distance to borders
            int top = i;
            int left = j;
            int right = len - 1 - j;
            int bottom = len - 1 - i;

            min = top;
            if (left < min)
                min = left;
            if (right < min)
                min = right;
            if (bottom < min)
                min = bottom;

            printf("%d ", n - min);
        }
        printf("\n");
    }

    return 0;
}
```




Output:

<img width="823" height="265" alt="image" src="https://github.com/user-attachments/assets/d490ecd0-0cee-4706-930a-64174cf36d74" />

<img width="822" height="426" alt="image" src="https://github.com/user-attachments/assets/9f92653a-98cb-4ebb-b1dc-e459a15fc664" />


Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

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

// Function declaration
int square();

int main()
{
    int result;

    // Call function and store returned value
    result = square();

    // Display result
    printf("Square of the number is: %d\n", result);

    return 0;
}

// Function definition
int square()
{
    int num;

    // Input inside function
    printf("Enter a number: ");
    scanf("%d", &num);

    // Return square
    return num * num;
}
```




Output:

<img width="819" height="231" alt="image" src="https://github.com/user-attachments/assets/1187d297-c811-4c3d-80a0-de2b74a3489d" />

Result:
Thus, the program is verified successfully









