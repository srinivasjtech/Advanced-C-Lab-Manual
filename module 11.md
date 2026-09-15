# EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER

## Aim:
To write a C program to create a function to find the greatest number

## Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
## Program:

```c
#include <stdio.h>

int max_of_four(int a, int b, int c, int d) {
    if (a >= b && a >= c && a >= d)
        return a;
    else if (b >= a && b >= c && b >= d)
        return b;
    else if (c >= a && c >= b && c >= d)
        return c;
    else
        return d;
}

int main() {
    int n1, n2, n3, n4, greater;

    printf("Enter four integers: ");
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);

    greater = max_of_four(n1, n2, n3, n4);

    printf("The greatest number is: %d\n", greater);

    return 0;
}

```

## Output:

<img width="623" height="186" alt="651985854-0fc48f7a-5ea8-49c2-b60d-1ad36ac32579" src="https://github.com/user-attachments/assets/8dfe2e4e-7db6-41af-8d53-32e22be311f1" />

## Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
# EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS

## Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

## Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
## Program:

```c
#include <stdio.h>

void calculate_the_maximum(int n, int k) {
    int maxA = 0, maxO = 0, maxX = 0;
    
    for (int a = 1; a < n; a++) {
        for (int b = a + 1; b <= n; b++) {
            int andV = a & b;
            int orV = a | b;
            int xorV = a ^ b;
            
            if (andV < k && andV > maxA) {
                maxA = andV;
            }
            if (orV < k && orV > maxO) {
                maxO = orV;
            }
            if (xorV < k && xorV > maxX) {
                maxX = xorV;
            }
        }
    }
    
    printf("%d\n%d\n%d\n", maxA, maxO, maxX);
}

int main() {
    int n, k;
    scanf("%d %d", &n, &k);
    calculate_the_maximum(n, k);
    return 0;
}


```

## Output:

<img width="508" height="628" alt="651986170-ab8d8372-de5d-4490-a1d2-748eeb5fe560" src="https://github.com/user-attachments/assets/b0503742-506c-4824-9655-6423ac360f57" />


## Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
# EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS

## Aim:
To write a C program to write the logic for the requests

## Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
## Program:

```c
#include <stdio.h>
#include <stdlib.h>
int* shelves[1000]; 
int bookcount[1000] = {0}; 

int main() 
{
    int n, q;
    scanf("%d %d", &n, &q);

    while (q--)
    {
        int type, x, y;
        scanf("%d", &type);

        if (type == 1)
        {
            scanf("%d %d", &x, &y);
            shelves[x] = realloc(shelves[x], (bookcount[x] + 1) * sizeof(int));
            shelves[x][bookcount[x]++] = y;
        } 
        else if (type == 2) 
        {
            scanf("%d %d", &x, &y);
            printf("%d\n", shelves[x][y]);
        } 
        else if (type == 3) 
        { 
            scanf("%d", &x);
            printf("%d\n", bookcount[x]);
        }
    }

    return 0;
}


```

## Output:

<img width="657" height="580" alt="651986564-05ca4548-87bc-4eac-9f4a-31ef439900e4" src="https://github.com/user-attachments/assets/9d4fc5e5-bc52-4aca-ae20-02a4fd5c632c" />


## Result:
Thus, the program to write the logic for the requests is verified successfully.


 
# EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.

## Aim:
To write a C program print the sum of the integers in the array.

## Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



## Program:

```c

#include <stdio.h>
#include <stdlib.h>

int main() {
    int n, sum = 0;
    scanf("%d", &n);
    
    int *arr = (int*)malloc(n * sizeof(int));
    if (arr == NULL) {
        return 1;
    }
    
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
        sum += arr[i];
    }
    
    printf("%d\n", sum);
    
    free(arr);
    return 0;
}

```

## Output:

<img width="646" height="405" alt="651986844-7d8431ee-1b7f-4f97-b41b-da091ae7fd25" src="https://github.com/user-attachments/assets/e037c12b-0fbe-41ab-92a6-7af78da4e954" />
 

## Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
# EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A SENTENCE



## Aim:

To write a C program that counts the number of words in a given sentence.

## Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



## Program:

```c
#include <stdio.h>

int main() {
    char sentence[100];
    int i = 0, words = 0;
    int inWord = 0;

    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);

    while (sentence[i] != '\0') {
        if (sentence[i] != ' ' && sentence[i] != '\n') {
            if (inWord == 0) {
                words++;
                inWord = 1;
            }
        } else {
            inWord = 0;
        }
        i++;
    }

    printf("The number of words in the sentence is: %d\n", words);

    return 0;
}



```

## Output:

<img width="636" height="152" alt="651987038-f0871ae5-ec3b-4df6-8d2c-e3b2edee7a70" src="https://github.com/user-attachments/assets/5ae10753-8f3b-4230-8b3d-47452330b211" />


## Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
