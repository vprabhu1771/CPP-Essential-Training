Here’s a list of commonly used topics and features from the `iomanip` header in C++:

### 🔹 Basics of `iomanip`

* Purpose: Used to control **input/output formatting** in C++.
* Included via: `#include <iomanip>`

---

### 🔸 Output Formatting Manipulators

#### **1. Width and Fill**

* `std::setw(n)` – Set field width.
* `std::setfill(c)` – Set fill character for padding.

#### **2. Precision**

* `std::setprecision(n)` – Set number of digits to display (for floating-point).

#### **3. Fixed and Scientific**

* `std::fixed` – Use fixed-point notation.
* `std::scientific` – Use scientific notation.
* `std::defaultfloat` – Revert to default float format.

#### **4. Alignment**

* `std::left` – Left-align output.
* `std::right` – Right-align output.
* `std::internal` – Place fill characters between sign and number.

#### **5. Show Base, Positive Sign, Trailing Zeros**

* `std::showbase` / `std::noshowbase` – Show base prefix (`0x`, `0`).
* `std::showpos` / `std::noshowpos` – Show `+` sign for positive numbers.
* `std::showpoint` / `std::noshowpoint` – Show decimal point and trailing zeros.

#### **6. Number Base**

* `std::dec` – Decimal format.
* `std::hex` – Hexadecimal format.
* `std::oct` – Octal format.
* `std::uppercase` / `std::nouppercase` – Upper/lower case for hex digits.

#### **7. Boolean Format**

* `std::boolalpha` – Show `true`/`false` instead of `1`/`0`.
* `std::noboolalpha` – Revert to numeric boolean.

---

### 🔸 Input Formatting (less commonly used)

* `std::skipws` / `std::noskipws` – Skip or include whitespace in input.
* `std::setbase(n)` – Set input number base (8, 10, or 16).

---

### 🔸 Practical Use Cases

* Tabular data output.
* Formatted floating-point output.
* Base conversion and representation.
* Pretty-printing logs or reports.

---

Let me know if you want **code examples** for any of these topics.

Sure! Here's a **separate C++ code example for each `iomanip` topic** with its **expected output**. Each block contains a simple `main()` function and focuses on **only one topic** for clarity.

---

### ✅ 1. `std::setw()` and `std::setfill()`

```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    cout << setw(10) << setfill('*') << 123 << endl;
    return 0;
}
```

**Output:**

```
*******123
```

---

### ✅ 2. `std::setprecision()`

```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    double pi = 3.1415926535;
    cout << setprecision(4) << pi << endl;
    return 0;
}
```

**Output:**

```
3.142
```

---

### ✅ 3. `std::fixed`

```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    double value = 12.34567;
    cout << fixed << setprecision(2) << value << endl;
    return 0;
}
```

**Output:**

```
12.35
```

---

### ✅ 4. `std::scientific`

```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    double value = 1234.56;
    cout << scientific << setprecision(2) << value << endl;
    return 0;
}
```

**Output:**

```
1.23e+03
```

---

### ✅ 5. `std::left`, `std::right`, `std::internal`

```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    cout << "|" << left << setw(10) << 123 << "|" << endl;
    cout << "|" << right << setw(10) << 123 << "|" << endl;
    cout << "|" << internal << setw(10) << -123 << "|" << endl;
    return 0;
}
```

**Output:**

```
|123       |
|       123|
|-       123|
```

---

### ✅ 6. `std::showbase` with `std::hex` and `std::oct`

```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    int num = 255;
    cout << showbase << hex << num << endl;
    cout << showbase << oct << num << endl;
    return 0;
}
```

**Output:**

```
0xff
0377
```

---

### ✅ 7. `std::showpos`

```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    cout << showpos << 25 << " " << -25 << endl;
    return 0;
}
```

**Output:**

```
+25 -25
```

---

### ✅ 8. `std::showpoint`

```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    cout << showpoint << fixed << setprecision(2) << 25.0 << endl;
    return 0;
}
```

**Output:**

```
25.00
```

---

### ✅ 9. `std::dec`, `std::hex`, `std::oct`

```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    int num = 100;
    cout << dec << num << " "
         << hex << num << " "
         << oct << num << endl;
    return 0;
}
```

**Output:**

```
100 64 144
```

---

### ✅ 10. `std::boolalpha`

```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    cout << boolalpha << true << " " << false << endl;
    return 0;
}
```

**Output:**

```
true false
```

---

### ✅ 11. `std::noboolalpha`

```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    cout << noboolalpha << true << " " << false << endl;
    return 0;
}
```

**Output:**

```
1 0
```

---

Let me know if you want these bundled together or want more advanced formatting examples!
