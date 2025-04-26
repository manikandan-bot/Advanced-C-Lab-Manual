
NAME: T.MANIKANDAN
-----------------
REG NO: 212224110037
-----------------

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

int main() {
    int n;
    
    printf("Enter a number: ");
    if (scanf("%d", &n) != 1) {
        printf("Invalid input\n");
        return 1;
    }

    switch(n) {
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
            printf("Number is not between 5 and 13\n");
    }
    
    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/11897205-a759-4c45-a46c-51dcbd6f7e13)



![image](https://github.com/user-attachments/assets/0d104723-5293-46e0-bd59-5cbe015ffea4)


Result:
Thus, the program is verified successfully
___________________________________________________________________________________________________________________________________________________________________
 
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

int main() {
    char a[50];
    int i, c, h;
    
    printf("Enter a string: ");
    scanf("%s", a);

    for (h = 0; h <= 3; h++) {
        c = 0;
        for (i = 0; i < strlen(a); i++) {
            if (a[i] == (h + '0')) {
                c++;
            }
        }
        printf("%d ", c);
    }
    
    return 0;
}
```

Output:



![image](https://github.com/user-attachments/assets/70167f89-f4cc-4ab4-8d69-2f109ac6872e)

Result:
Thus, the program is verified successfully
___________________________________________________________________________________________________________________________________________________________________

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

void swap(char **a, char **b) {
    char *temp = *a;
    *a = *b;
    *b = temp;
}

void permute(char **s, int l, int r) {
    if (l == r) {
        for (int i = 0; i <= r; i++) {
            printf("%s ", s[i]);
        }
        printf("\n");
    } else {
        for (int i = l; i <= r; i++) {
            swap(&s[l], &s[i]);
            permute(s, l + 1, r);
            swap(&s[l], &s[i]);
        }
    }
}

int main() {
    char **s;
    int n, i;
    
    printf("Enter the number of strings: ");
    scanf("%d", &n);

    s = (char **)malloc(n * sizeof(char *));
    for (i = 0; i < n; i++) {
        s[i] = (char *)malloc(100 * sizeof(char));
        scanf("%s", s[i]);
    }

    permute(s, 0, n - 1);

    for (i = 0; i < n; i++) {
        free(s[i]);
    }
    free(s);
    
    return 0;
}
```

Output:



![image](https://github.com/user-attachments/assets/4001f504-f434-469e-9981-8aa9cc51c498)

Result:
Thus, the program is verified successfully
 __________________________________________________________________________________________________________________________________________________________________

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

int main() {
    int n, len, i, j, min;
    
    printf("Enter n: ");
    scanf("%d", &n);
    
    len = n * 2 - 1;
    
    for (i = 0; i < len; i++) {
        for (j = 0; j < len; j++) {
            min = i < j ? i : j;
            min = min < len - i ? min : len - i - 1;
            min = min < len - j - 1 ? min : len - j - 1;
            printf("%d ", n - min);
        }
        printf("\n");
    }
    
    return 0;
}
```

Output:


![image](https://github.com/user-attachments/assets/ad36619c-dceb-4363-9425-c60c088e1f09)



Result:
Thus, the program is verified successfully
___________________________________________________________________________________________________________________________________________________________________

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

int square() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    return num * num;
}

int main() {
    int result;
    result = square();
    printf("Square is: %d\n", result);
    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/233fbe04-17b7-4500-aed1-b6fd1dec370a)



Result:
Thus, the program is verified successfully



























