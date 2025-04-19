
## Declaration before call - ✅
```C
#include <stdio.h>

// Function declaration
void greet();

void caller() {
    greet();  // call before definition, works due to declaration
}

// Function definition
void greet() {
    printf("Hello!\n");
}

int main() {
    caller();
    return 0;
}
```

## Definition after function calling without declaration - ❌
```C
#include <stdio.h>

void caller() {
    greet();  // Error: 'greet' is undeclared
}

// Function definition after use
void greet() {
    printf("Hello!\n");
}

int main() {
    caller();
    return 0;
}
```

❗ Without a declaration before the call, the compiler throws an "implicit declaration" error in modern C (e.g. C99 and later).
Always declare functions before calling them if they are defined later.
