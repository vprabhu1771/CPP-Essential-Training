#include <iostream>
#include <cstring>  // For strcpy
using namespace std;

#define size 100

class product {
private:
    int product_no, price, qty, total;
    char *product_name;
public:
    product() {
        product_name = new char[size];  // Allocate memory for product_name
    }

    ~product() {
        delete[] product_name;  // Deallocate memory for product_name
    }

    void get_product_details(int no, const char* name, int p, int q) {
        product_no = no;
        strcpy(product_name, name);  // Copy name into product_name
        price = p;
        qty = q;
        total = p * q;
    }

    void print_product_details() const {
        cout << "Product No : " << product_no << endl;
        cout << "Product Name : " << product_name << endl;
        cout << "Price : " << price << endl;
        cout << "Quantity : " << qty << endl;
        cout << "Total : " << total << endl;
    }
};

int main() {
    product p1;
    p1.get_product_details(121, "Apple", 10, 2);
    p1.print_product_details();  // Added print function call to see the result
    return 0;
}

Product No : 121
Product Name : Apple
Price : 10
Quantity : 2
Total : 20
