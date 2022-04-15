- [Home](home)

# Structs 

Datum: 15/04/2022 
Tags: C++ 
Téma: Structs 

```cpp 
struct Fraction 
{ 
int numerator {}; 
int denominator {}; 
}; 

// Now we can make use of our Fraction type 
int main() 
{ 
Fraction f{ 3, 4 }; // this actually instantiates a Fraction object named f 

return 0; 
} 
``` 

Structs are user defined variables kinda like when we use: 

```cpp 
using lenght = int; 
``` 

Then we can use lenght as variable type and it will be used as int 

--- 

### Using structs in header file 

```cpp 
// main.h 

#ifndef FRACTION_H 
#define FRACTION_H 

struct Fraction 
{ 
int numerator {}; 
int denominator {}; 
}; 

#endif 
``` 

```cpp 
// main.cpp 

#include "Fraction.h" 

int main() 
{ 
Fraction f{ 3, 4 }; 

return 0; 
} 
```
