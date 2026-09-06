EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
Program:

#include <stdio.h>

struct eligible {
    int age;
    char n[50];
};

int main() {
    struct eligible e;

    // Input age and name
    printf("Enter age: ");
    scanf("%d", &e.age);

    printf("Enter name: ");
    scanf("%s", e.n);

    // Check vaccine eligibility
    if (e.age <= 6) {
        printf("Vaccine Eligibility: No\n");
    } else {
        printf("Vaccine Eligibility: Yes\n");
    }

    // Print details
    printf("Age: %d\n", e.age);
    printf("Name: %s\n", e.n);

    return 0;
}


Output:

Enter age: 5
Enter name: Arun
Vaccine Eligibility: No
Age: 5
Name: Arun


Result:
Thus, the program is verified successfully. 



EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
Aim:
To write a C program for passing structure as function and returning a structure from a function

Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
Program:

#include <stdio.h>

struct numbers {
    int a;
    int b;
};

int add(struct numbers n) {
    return n.a + n.b;
}

int main() {
    struct numbers n;
    int result;

    printf("Enter value of a: ");
    scanf("%d", &n.a);

    printf("Enter value of b: ");
    scanf("%d", &n.b);

    result = add(n);

    printf("Sum = %d\n", result);

    return 0;
}




Output:


Enter value of a: 10
Enter value of b: 20
Sum = 30




Result:
Thus, the program is verified successfully


 
EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim:
To write a C program to read a file name from user

Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare a character array name to store the file name.
4.	Prompt the user to enter a file name.
Use scanf to input the file name into the name array.
5.	Print a message indicating that the file with the specified name has been created successfully.
6.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
1.	Print a message indicating that the file has been opened successfully.
2.	Use fclose to close the file.
3.	Print a message indicating that the file has been closed.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:

#include <stdio.h>

int main() {
    FILE *p;
    char name[100];

    printf("Enter file name: ");
    scanf("%s", name);

    p = fopen(name, "w");

    if (p == NULL) {
        printf("Error: File could not be created.\n");
        return 1;
    }

    printf("File '%s' has been created successfully.\n", name);
    printf("File opened successfully.\n");

    fclose(p);

    printf("File closed successfully.\n");

    return 0;
}




Output:


Enter file name: sample.txt
File 'sample.txt' has been created successfully.
File opened successfully.
File closed successfully.











Result:
Thus, the program is verified successfully
 


EXP NO:4   PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE
Aim:
To write a C program to read, a file and insert text in that file
Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare character arrays name and text. Declare an integer variable num.
4.	Prompt the user to enter a file name and the number of strings.
Use scanf to input the file name into the name array and the number of strings into the num variable.
5.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
6.	Print a message indicating that the file has been opened successfully.
1.	Use a loop to input strings from the user and write them to the file using fputs.
2.	Use fclose to close the file.
3.	Print a message indicating that data has been added successfully.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:

#include <stdio.h>

int main() {
    FILE *p;
    char name[100];
    char text[100];
    int num, i;

    printf("Enter file name: ");
    scanf("%s", name);

    printf("Enter number of strings: ");
    scanf("%d", &num);

    p = fopen(name, "w");

    if (p == NULL) {
        printf("Error: File could not be opened.\n");
        return 1;
    }

    printf("File opened successfully.\n");

    // Input strings and write them to the file
    for (i = 0; i < num; i++) {
        printf("Enter string %d: ", i + 1);
        scanf("%s", text);

        fputs(text, p);
        fputs("\n", p);
    }

    fclose(p);

    printf("Data has been added successfully.\n");

    return 0;
}



Output:


Enter file name: sample.txt
Enter number of strings: 3
File opened successfully.
Enter string 1: Hello
Enter string 2: Welcome
Enter string 3: Cprogram
Data has been added successfully.






Result:
Thus, the program is verified successfully



Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm:
1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.

Program:

#include <stdio.h>
#include <stdlib.h>

struct subject {
    char name[50];
    int marks;
};

int main() {
    int n, i;
    struct subject *s;

    // Input number of subjects
    printf("Enter number of subjects: ");
    scanf("%d", &n);

    // Dynamically allocate memory
    s = (struct subject *)malloc(n * sizeof(struct subject));

    // Check memory allocation
    if (s == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }

    // Input subject details
    for (i = 0; i < n; i++) {
        printf("Enter subject name: ");
        scanf("%s", s[i].name);

        printf("Enter marks: ");
        scanf("%d", &s[i].marks);
    }

    // Display subject details
    printf("\nSubject Details:\n");

    for (i = 0; i < n; i++) {
        printf("Subject: %s\n", s[i].name);
        printf("Marks: %d\n", s[i].marks);
    }

    // Free allocated memory
    free(s);

    return 0;
}




Output:


Enter number of subjects: 3

Enter subject name: Maths
Enter marks: 90

Enter subject name: Physics
Enter marks: 85

Enter subject name: Chemistry
Enter marks: 88

Subject Details:
Subject: Maths
Marks: 90
Subject: Physics
Marks: 85
Subject: Chemistry
Marks: 88






Result:
Thus, the program is verified successfully
