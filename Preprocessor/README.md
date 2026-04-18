The **C Preprocessor** is a tool that processes your code before compilation. It handles directives for macros, file inclusion, conditional compilation, and more. Preprocessor directives in C begin with the `#` symbol.

### 📄 **List of C Preprocessor Directives**

#### 1. **Macro Definition and Substitution**
- `#define` – Defines a macro.
  ```c
  #define PI 3.14159
  #define SQUARE(x) ((x) * (x))
  ```
- `#undef` – Undefines a macro.
  ```c
  #undef PI
  ```

---

#### 2. **File Inclusion**
- `#include` – Includes the contents of another file.
  - Angle brackets (`< >`) for standard library headers:
    ```c
    #include <stdio.h>
    ```
  - Double quotes (`" "`) for user-defined headers:
    ```c
    #include "myheader.h"
    ```

---

#### 3. **Conditional Compilation**
- `#ifdef` – Checks if a macro is defined.
  ```c
  #ifdef DEBUG
      printf("Debug mode\n");
  #endif
  ```

- `#ifndef` – Checks if a macro is *not* defined.
  ```c
  #ifndef VERSION
      #define VERSION "1.0"
  #endif
  ```

- `#if`, `#elif`, `#else`, `#endif` – Conditional checks.
  ```c
  #if defined(WINDOWS)
      printf("Windows OS\n");
  #elif defined(LINUX)
      printf("Linux OS\n");
  #else
      printf("Unknown OS\n");
  #endif
  ```

---

#### 4. **Macro Operators**
- `#` – Stringize operator (converts macro argument into a string).
  ```c
  #define STR(x) #x
  printf("%s\n", STR(Hello));  // Output: Hello
  ```

- `##` – Token-pasting operator (concatenates tokens).
  ```c
  #define CONCAT(a, b) a##b
  int CONCAT(num, 1) = 100;  // Creates variable num1
  ```

---

#### 5. **Other Directives**
- `#pragma` – Provides compiler-specific instructions.
  ```c
  #pragma once  // Prevents multiple inclusions of a header
  ```

- `#error` – Generates a compile-time error.
  ```c
  #ifndef CONFIG
      #error "CONFIG not defined!"
  #endif
  ```

- `#line` – Changes the compiler's idea of the current line number and file.
  ```c
  #line 100 "myfile.c"
  ```

---

#### 6. **Predefined Macros** *(Provided by the compiler)*
| **Macro** | **Description** |
|-----------|-----------------|
| `__FILE__` | Name of the current file |
| `__LINE__` | Current line number |
| `__DATE__` | Compilation date (e.g., "Feb 22 2025") |
| `__TIME__` | Compilation time (e.g., "14:30:00") |
| `__STDC__` | Defined if the compiler conforms to the C standard |

Example:
```c
printf("File: %s, Line: %d\n", __FILE__, __LINE__);
```

---

```
#include<stdio.h>
#include<stdlib.h>

int main()
{
    printf("%s", __FILE__);
    return 0;
}
```

```
#include<stdio.h>
#include<stdlib.h>

int main()
{
    printf("%d", __LINE__);
    return 0;
}
```

```
#include<stdio.h>
#include<stdlib.h>

int main()
{
    printf("%s", __DATE__);
    return 0;
}
```

```
#include<stdio.h>
#include<stdlib.h>

int main()
{
    printf("%s", __TIME__);
    return 0;
}
```

```
#include<stdio.h>
#include<stdlib.h>

int main()
{
    #ifdef __STDC__
    printf("The compiler conforms to the ANSI C standard.\n");
    #else
        printf("The compiler does not conform to the ANSI C standard.\n");
    #endif
    return 0;
}
```
