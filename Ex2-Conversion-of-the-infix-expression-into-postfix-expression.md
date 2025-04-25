# Ex2 Conversion of the infix expression into postfix expression
## DATE:20/02/2025
## AIM:
To write a C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule.

## Algorithm
1. Start the program.
2. Initialize a stack and set the top index to -1.
3. Define the push() and pop() functions to add and remove elements from the stack.
4. Define the priority() function to assign priorities to operators.
5. Traverse the expression in the IntoPost() function, handling operands, parentheses, and operators.
6. After processing the expression, pop and print any remaining operators from the stack.
7. End of the program.   

## Program:
```
/*
Program to convert the infix expression into postfix expression
Developed by: MOHAN S
RegisterNumber:  212223240094
*/
```
```
char IntoPost(char *exp)
{
    //write your code here
    char *e,x;
    e=exp;
    while(*e!='\0')
    {
        if(isalnum(*e))
        {
            printf("%c",*e);
        }
        else if(*e=='(')
        {
            push(*e);
        }
        else if(*e==')')
        {
            while((x=pop())!='(')
            {
                printf("%c",x);
            }
        }
        else
        {
            while(top!=-1 && priority(stack[top])>=priority(*e))
            {
                printf("%c",pop());
            }
            push(*e);
        }
        e++;
    }
    while(top!=-1)
    {
        printf("%c",pop());
    }

    
    
 return 1;   
}
```

## Output:
![Screenshot 2025-04-25 200826](https://github.com/user-attachments/assets/3f07e563-8171-42a7-8119-f42684136b27)


## Result:
Thus, the C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule is implemented successfully.
