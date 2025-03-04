File handling in C++ allows you to read from and write to files using the `<fstream>` library. Here’s a breakdown of the key concepts along with examples:

---

## **1. Include Required Library**
```cpp
#include <iostream>
#include <fstream>  // File handling library
```

---

## **2. Writing to a File (`ofstream`)**
```cpp
#include <iostream>
#include <fstream>

int main() {
    std::ofstream file("example.txt");  // Create and open a file
    if (file.is_open()) {
        file << "Hello, File Handling in C++!\n";
        file << "This is a test file.\n";
        file.close();  // Close the file
        std::cout << "File written successfully!" << std::endl;
    } else {
        std::cout << "Error opening file!" << std::endl;
    }
    return 0;
}
```
🔹 **Creates** a file named `example.txt` and writes text into it.

---

## **3. Reading from a File (`ifstream`)**
```cpp
#include <iostream>
#include <fstream>
#include <string>

int main() {
    std::ifstream file("example.txt");  // Open file for reading
    std::string line;
    
    if (file.is_open()) {
        while (getline(file, line)) {  // Read line by line
            std::cout << line << std::endl;
        }
        file.close();
    } else {
        std::cout << "Error opening file!" << std::endl;
    }
    return 0;
}
```
🔹 **Reads** the file `example.txt` line by line and displays the content.

---

## **4. Appending to a File (`ofstream` with `ios::app`)**
```cpp
#include <iostream>
#include <fstream>

int main() {
    std::ofstream file("example.txt", std::ios::app);  // Open file in append mode
    if (file.is_open()) {
        file << "Appending new content!\n";
        file.close();
        std::cout << "Content appended successfully!" << std::endl;
    } else {
        std::cout << "Error opening file!" << std::endl;
    }
    return 0;
}
```
🔹 **Appends** text instead of overwriting the file.

---

## **5. Checking if a File Exists**
```cpp
#include <iostream>
#include <fstream>

int main() {
    std::ifstream file("example.txt");
    if (file) {
        std::cout << "File exists!" << std::endl;
    } else {
        std::cout << "File does not exist!" << std::endl;
    }
    return 0;
}
```
🔹 Checks if a file exists before performing operations.

---

## **6. Read and Write Using `fstream`**
```cpp
#include <iostream>
#include <fstream>

int main() {
    std::fstream file("data.txt", std::ios::in | std::ios::out | std::ios::trunc);
    
    if (!file) {
        std::cout << "Error opening file!" << std::endl;
        return 1;
    }
    
    file << "Writing data to file.\n";
    file.seekg(0);  // Move cursor to the beginning for reading

    std::string line;
    while (getline(file, line)) {
        std::cout << line << std::endl;
    }

    file.close();
    return 0;
}
```
🔹 Opens a file for both **reading and writing** using `fstream`.

---

## **7. Binary File Handling**
### **Writing a Structure to a Binary File**
```cpp
#include <iostream>
#include <fstream>

struct Employee {
    char name[50];
    int age;
    double salary;
};

int main() {
    Employee emp = {"John Doe", 30, 50000.5};

    std::ofstream file("employee.dat", std::ios::binary);
    if (file.is_open()) {
        file.write(reinterpret_cast<char*>(&emp), sizeof(emp));
        file.close();
        std::cout << "Employee data saved!" << std::endl;
    } else {
        std::cout << "Error opening file!" << std::endl;
    }
    return 0;
}
```

### **Reading a Structure from a Binary File**
```cpp
#include <iostream>
#include <fstream>

struct Employee {
    char name[50];
    int age;
    double salary;
};

int main() {
    Employee emp;

    std::ifstream file("employee.dat", std::ios::binary);
    if (file.is_open()) {
        file.read(reinterpret_cast<char*>(&emp), sizeof(emp));
        file.close();
        std::cout << "Employee Name: " << emp.name << "\nAge: " << emp.age << "\nSalary: " << emp.salary << std::endl;
    } else {
        std::cout << "Error opening file!" << std::endl;
    }
    return 0;
}
```
🔹 **Binary file handling** is used for efficient storage and retrieval.

---

## **8. Deleting a File**
```cpp
#include <iostream>
#include <cstdio>

int main() {
    if (remove("example.txt") == 0) {
        std::cout << "File deleted successfully!" << std::endl;
    } else {
        std::cout << "Error deleting file!" << std::endl;
    }
    return 0;
}
```
🔹 Deletes a file using `remove()` function.

---

### 🔥 **Summary**
| Operation        | Class Used  | Mode Flag |
|-----------------|------------|-----------|
| Write to File   | `ofstream`  | `ios::out` (default) |
| Read from File  | `ifstream`  | `ios::in` (default) |
| Append to File  | `ofstream`  | `ios::app` |
| Read & Write    | `fstream`   | `ios::in | ios::out` |
| Binary File     | `fstream`   | `ios::binary` |

These examples demonstrate essential file handling operations in C++. Let me know if you need any modifications! 🚀
