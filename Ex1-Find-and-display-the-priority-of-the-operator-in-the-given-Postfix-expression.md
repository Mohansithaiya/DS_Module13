# EX 1 Display operator precedence in the infix expression.
## DATE:20/02/2025
## AIM:
To write a C program to find and display the priority of the operator in the given Postfix expression

## Algorithm
1. Start the program.
2. Define the priority() function to return the priority of operators.
3. Initialize the string containing operators and operands.
4. Loop through each character in the string.
5. For each operator, call the priority() function to determine its priority.
6. Print the operator and its corresponding priority level.
7. End of the program.

## Program:
```
/*
Program to find and display the priority of the operator in the given Postfix expression
Developed by: MOHAN S 
RegisterNumber:  212223240094
*/
```
```
#include <stdio.h>

int getPriority(char op) {
    switch (op) {
        case '&': return 1; 
        case '+': return 2;  
        case '*': 
        case '%': 
        case '/': return 3;  
        case '^': return 4;  
        default: return 0; 
    }
}

void displayPriority(char op) {
    switch (getPriority(op)) {
        case 1: printf("%c  ----> Lowest Priority\n", op); break;
        case 2: printf("%c  ----> Second Lowest Priority\n", op); break;
        case 3: printf("%c  ----> Second Highest Priority\n", op); break;
        case 4: printf("%c  ----> Highest Priority\n", op); break;
    }
}

int main() {
    char operators[] = {'*', '^', '+', '%', '/', '&'};
    

    for (int i = 0; i < sizeof(operators)/sizeof(operators[0]); i++) {
        displayPriority(operators[i]);
    }
    
    return 0;
}
```



## Output:
![Screenshot 2025-04-25 200405](https://github.com/user-attachments/assets/41097a7e-c538-4de2-9cb7-2af94bdeff6b)


## Result:
Thus the C program to find and display the priority of the operator in the given Postfix expression is implemented successfully
