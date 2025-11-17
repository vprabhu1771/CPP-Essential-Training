```
#include<iostream>

// Template function to return maximum of two values
template <typename T> T max(T x, T y)
{
	return (x > y) ? x : y;
}

int main()
{

    std::cout << max(2,10) << std::endl;

    std::cout << max(2.0, 10.0) << std::endl;

    std::cout << max('a', 'b') << std::endl;

	return 0;
}
```
