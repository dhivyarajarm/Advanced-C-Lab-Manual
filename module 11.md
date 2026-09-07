

EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
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

// Function to find maximum of four numbers
int max_of_four(int n1, int n2, int n3, int n4)
{
    if (n1 >= n2 && n1 >= n3 && n1 >= n4)
        return n1;
    else if (n2 >= n1 && n2 >= n3 && n2 >= n4)
        return n2;
    else if (n3 >= n1 && n3 >= n2 && n3 >= n4)
        return n3;
    else
        return n4;
}

int main()
{
    int n1, n2, n3, n4, greater;

    printf("Enter four integers: ");
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);

    greater = max_of_four(n1, n2, n3, n4);

    printf("Greater number = %d", greater);

    return 0;
}
```

Output:
Enter four integers: 10 25 15 20
Greater number = 25

Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
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
            // AND
            if ((i & j) < k && (i & j) > a)
                a = i & j;

            // OR
            if ((i | j) < k && (i | j) > o)
                o = i | j;

            // XOR
            if ((i ^ j) < k && (i ^ j) > x)
                x = i ^ j;
        }
    }

    printf("%d\n", a);
    printf("%d\n", o);
    printf("%d\n", x);
}

int main()
{
    int n, k;

    scanf("%d %d", &n, &k);

    calculate_the_max(n, k);

    return 0;
}
```

Output:
2
3
3

Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
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

int main()
{
    int noshel, noque;

    // 1 & 2. Number of shelves and queries
    scanf("%d %d", &noshel, &noque);

    // 3. 2D array for shelves and books
    int shelarr[noshel][noque];
    int nobookarr[noshel];

    // Initialize number of books in each shelf to 0
    for (int i = 0; i < noshel; i++)
    {
        nobookarr[i] = 0;
    }

    // 4. Variables
    int k, c;

    // 5. Iterate over queries
    for (int i = 0; i < noque; i++)
    {
        int type, x, y;

        scanf("%d %d %d", &type, &x, &y);

        if (type == 1)
        {
            // Add book y to shelf x
            c = nobookarr[x];

            shelarr[x][c] = y;

            nobookarr[x]++;
        }
        else if (type == 2)
        {
            // Display book at index y in shelf x
            k = shelarr[x][y];

            printf("%d\n", k);
        }
        else if (type == 3)
        {
            // Display number of books in shelf x
            printf("%d\n", nobookarr[x]);
        }
    }

    return 0;
}
```

Output:
5 5
1 0 15
1 0 20
1 1 30
2 0 1
3 0 0


Result:
Thus, the program to write the logic for the requests is verified successfully.


 
EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
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
    // 1. Declare n
    int n;

    // 2. Input n
    scanf("%d", &n);

    // 3. Declare array
    int a[n];

    // 4. Initialize sum to zero
    int sum = 0;

    // 5 & 6. Input n integers and calculate sum
    for (int i = 0; i < n; i++)
    {
        scanf("%d", &a[i]);
        sum = sum + a[i];
    }

    // 7. Print final sum
    printf("%d", sum);

    return 0;
}
```
Output:
150
 


Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A      SENTENCE



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
    char sentence[200];
    int count = 0;
    int inWord = 0;

    // 1. Input the sentence
    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);

    // 2 & 3. Process each character
    for (int i = 0; sentence[i] != '\0'; i++)
    {
        // If character is not a space
        if (sentence[i] != ' ' && sentence[i] != '\n' &&
            sentence[i] != '\t')
        {
            // First character of a new word
            if (inWord == 0)
            {
                count++;
                inWord = 1;
            }
        }
        else
        {
            // Space means word has ended
            inWord = 0;
        }
    }

    // 5. Display result
    printf("Number of words = %d", count);

    return 0;
}
```
Output:
Enter a sentence: Hello world how are you
Number of words = 5



Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
