# CPP-Essential-Training
 
You're almost there! The issue is that `setprecision(2)` **doesn't affect the number of digits after the decimal point** by default—it affects the **total number of significant digits**.

To make `setprecision(2)` show exactly **2 digits after the decimal**, you need to use `fixed` along with it. Here's the corrected version of your code:

```cpp
#include<iostream>
#include<iomanip>
using namespace std;

int main()
{
    float x, y;
    cout << "Enter x value\n";
    cin >> x;
    cout << "Enter y value\n";
    cin >> y;

    cout << fixed << setprecision(2); // set fixed-point notation and precision to 2 digits after decimal
    cout << "x value is " << x << "\n";
    cout << "y value is " << y << "\n";

    return 0;
}
```

### Example Output:
```
Enter x value
3.14159
Enter y value
2.71828
x value is 3.14
y value is 2.72
```

Let me know if you also want to show trailing zeroes like `3.00`, etc.
