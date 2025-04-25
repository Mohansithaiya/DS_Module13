# Ex4 Evaluation of prefix expression
## DATE:24/02/2025
## AIM:
To write a C function to evaluate the given prefix expression using stack and print the output of the given prefix expression from the stack inside the function . 

## Algorithm
1. Start the program.
2. Initialize an empty stack s with a variable top for tracking the stack index.
3. Define a push() function to add an element to the stack.
4. Define a pop() function to remove and return the top element from the stack.
5. In evalprefix(), loop through the given prefix expression from right to left.
6. For each character, if it’s an operator (-,*), pop two operands from the stack, perform the operation, and push the result.
7. If it's a digit, convert it to an integer and push it onto the stack; finally, print the result after the loop ends.
8. End of the program.  

## Program:
```
/*
Program to evaluate the given prefix expression
Developed by: MOHAN S
RegisterNumber:  212223240094
*/
```
```
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int s[50];
int top=0;

void push(int ch)
{

	s[++top]=ch;
}

int pop()
{
// 	int ch;
// 	ch=s[top];
// 	top=top-1;
// 	return(ch);
    return s[top--];
}

void evalprefix(char p[50])
{
    int n,n1,n2,n3;
    int i = strlen(p) - 1;
    while(i>=0){
        if(isdigit(p[i])){
            n=p[i] - 48;
            push(n);
        }
        else{
            n1=pop();
            n2=pop();
            switch(p[i]){
                case '-':
                n3=n1-n2;
                break;
                case '*':
                n3=n1*n2;
                break;
            }
            push(n3);
        }
        i--;
    }
    printf("%d",pop());
}

```

## Output:
![Screenshot 2025-04-25 201829](https://github.com/user-attachments/assets/3143fa6c-ed33-4ef5-b4e6-0848b043aba1)


## Result:
Thus, the C program to evaluate the prefix expression using stack and print the output of the given prefix expression from the stack inside the function is implemented successfully.
