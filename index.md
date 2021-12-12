->> const-usage:

\The const keyword allows you to specify whether or not a variable is modifiable. \You can use const to prevent modifications to variables and const pointers and const references prevent changing the data pointed to (or referenced)

1- Const Variable:
```
int const x = 5; 
const int x = 4;
```
\result in x's being a constant integer. Note that in both cases, the value of the variable is specified in the declaration; \there's no way to set it later!

2- Const Pointers:
```
const int *p_int; 
```
\You can think of this as reading that *p_int is a "const int". So the pointer may be changeable, but you definitely can't touch what p_int points to. \The key here is that the const appears before the *.
```
int x;
int * const p_int = &x; 
```
\the value stored in p_int itself cannot change--so you just can't change the address pointed to.

3- Const Functions:
```
<return-value> <class>::<member-function>( <args> ) const
{
    \\.......
}
int Loan::calcInterest() const
{ 
return loan_value * interest_rate; 
} 
```
\if you have a const function, all that means is that it guarantees it won't change the object. \So just because it is const doesn't mean that non-const objects can't use it.

   4- Const Overloading:
   ```
int& myClass::getData() 
{
return data;
}
```
// called for const objects only since a non-const version also exists 
```
const int& myData::getData() const {
return data;
}
```
5- Const iterators:
```
std::vector vec; 
vec.push_back( 3 );
vec.push_back( 4 );
vec.push_back( 8 );
for ( std::vector::const_iterator itr = vec.begin(), end = vec.end();
itr != end;
++itr ) 
{ // just print out the values... std::cout<< *itr <<std::endl; 
} 
```
\it prevents the possibility of silly programming mistakes

 6- Const cast:
\\Const casts look like regular typecasts in C++, 
\\except that they can only be used for casting away constness (or volatile-ness) 
\\but not converting between types or casting down a class hierarchy.

// a bad version of strlen that doesn't declare its argument const
```
int bad_strlen (char *x)
{
strlen( x );
}

// note that the extra const is actually implicit in this declaration since
// string literals are constant
const char *x = "abc";

// cast away const-ness for our strlen function
bad_strlen( const_cast<char *>(x) );
```

->> &-usage:

 1- Bitwise AND:
 ```
#include <iostream>  
using namespace std;

int main() {  
unsigned short a = 0x5555;      // pattern 0101 ...  
unsigned short b = 0xAAAA;      // pattern 1010 ...

cout << hex << ( a & b ) << endl;
}
```
2- Address Of operator:
```
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
```

3- Bitwise-and-assign:
```
x &= y; 
Means the same as: x = x&y;
```
