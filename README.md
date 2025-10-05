# To-check-a-string-is-valid-parenthesis-or-not-
To write a C program that checks whether a given string of parentheses is balanced or not using a stack.
#include <stdio.h>
#include <string.h>

#define MAX 100 


int isBalanced(char str[]) {
    char stack[MAX];
    int top = -1;  

    for (int i = 0; i < strlen(str); i++) {
        
        if (str[i] == '(' || str[i] == '{' || str[i] == '[') {
            stack[++top] = str[i]
        else if (str[i] == ')' || str[i] == '}' || str[i] == ']') {
            if (top == -1)   empty → no matching opening bracket
                return 0;

            char popped = stack[top--]; 

          
            if ((str[i] == ')' && popped != '(') ||
                (str[i] == '}' && popped != '{') ||
                (str[i] == ']' && popped != '['))
                return 0;
        }
    }

    // If stack is empty → balanced, else not balanced
    return (top == -1);
}

// Main function
int main() {
    char str[MAX];

    printf("Enter a string of parentheses: ");
    scanf("%s", str);

    if (isBalanced(str))
        printf("Balanced Parentheses \n");
    else
        printf("Not Balanced \n");

    return 0;
}
