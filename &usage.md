
1- Bitwise AND:

#include <iostream>  
using namespace std;

int main() {  
unsigned short a = 0x5555;      // pattern 0101 ...  
unsigned short b = 0xAAAA;      // pattern 1010 ...

cout << hex << ( a & b ) << endl;
}

2- Address Of operator:

#include <iostream>  
using namespace std;

int main () {
int  var;
int  *ptr;
int  val;

var = 3000;

// take the address of var
ptr = &var;

// take the value available at ptr
val = *ptr;
cout << "Value of var :" << var << endl;
cout << "Value of ptr :" << ptr << endl;
cout << "Value of val :" << val << endl;

return 0;
}

3- Bitwise-and-assign:

   x &= y; 
Means the same as: 
  x = x&y;