# Stack

```c
#include <stdio.h>

int stack[100], i, j, n, top = -1, choice, value;

//declaration of function
//in declaration, only function signature is used
//function signature - return_type function_name()
//WHY ?
//Because these functions are being defined after calling
//If these were defined before calling, then this declaration wasn't needed
void push();
// void show();
void pop();

//function definition
//entire logic of the function is put here
void show(){
    for(i= top; i>=0; i--){
        printf("%d ", stack[i]);
    }
    if(top == -1){
        printf("\nStack is empty!!");
    }
}

int main()
{
    printf("Enter the no. of elements in the stack ");
    scanf("%d", &n);
     while(1) {
        printf("\n--- Stack Menu ---\n");
        printf("1. Push\n2. Pop\n3. Display\n4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch(choice) {
            case 1:
                push();
                show();
                break;
            case 2:
                pop();
                show();
            case 3:
                show();
                break;
            case 4:
                printf("Exiting program.\n");
                return 0;
            default:
                printf("Invalid choice! Please enter 1, 2, or 3.\n");
        }
    }
    return 0;
}

void pop(){
    int val;
    val = stack[top];
    top--;
    printf("Popped value: %d", val);
    // return val;
}

void push()
{
    int val;
    if (top == n-1)
    {
        printf("\n Overflow ");
    }
    else
    {
        printf("Enter the value: ");
        scanf("%d", &val);

        top = top + 1;
        stack[top] = val;
    }
}
```
