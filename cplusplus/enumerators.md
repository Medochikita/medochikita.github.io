- [Home](home)

# Enumerators 

Datum: 15/04/2022 
Tags: C++ 
Téma: Enumerators 

```cpp 
#include <iostream> 

enum Color 
{ 
black, // assigned 0 
red, // assigned 1 
blue, // assigned 2 
green, // assigned 3 
white, // assigned 4 
cyan, // assigned 5 
yellow, // assigned 6 
magenta, // assigned 7 
}; 

int main() 
{ 
Color shirt{ blue }; // This actually stores the integral value 2 

return 0; 
} 
``` 

```cpp 
enum Animal 
{ 
cat = -3, 
dog, // assigned -2 
pig, // assigned -1 
horse = 5, 
giraffe = 5, // shares same value as horse 
chicken, // assigned 6 
}; 
``` 

We can also explicitly define the values of the elements 

```cpp 
#include <iostream>enum Color 
{ 
black, // assigned 0 
red, // assigned 1 
blue, // assigned 2 
green, // assigned 3 
white, // assigned 4 
cyan, // assigned 5 
yellow, // assigned 6 
magenta, // assigned 7 
}; 

int main() 
{ 
Color shirt{ blue }; 

std::cout << "Your shirt is " << shirt; // what does this do? 

return 0; 
} 
``` 

This code will output: 

``` 
Your shirt is 2 
``` 

We can instead return the string value using switch cases 

```cpp 
#include <iostream> 
#include <string> 
enum Color 
{ 
black, 
red, 
blue, 
}; 

std::string getColor(Color color) 
{ 
switch (color) 
{ 
case black: return "black"; 
case red: return "red"; 
case blue: return "blue"; 
default: return "???"; 
} 
} 

int main() 
{ 
Color shirt { blue }; 

std::cout << "Your shirt is " << getColor(shirt) << '\n'; 

return 0; 
} 
``` 

This will output: 

``` 
Your shirt is blue 
```
