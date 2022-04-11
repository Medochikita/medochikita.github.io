# Pokračování základního programu 

Datum: 04/04/2022 
Tags: C++ 
Téma: Základní program vol. 2 

```cpp 
#include <iostream> 
using namespace std; 

int main() 
{ 

int yearofbirth = 1995; 
char gender = "f"; 
bool isOlderThan18 = true; 
float avaregeGrade = 4.5; 
double accBalance = 451364821; 

cout << "size of int is: " << sizeof(int) << " bytes" << endl; 
cout << "size of double is: " << sizeof(double) << "bytes" << endl; 

// 4 bytes - int 
// 8 bytes - double 

cout << int("a") << endl; // 97 
cout << char("97") << endl; // a 

return 0; 
} 
``` 

### Vysvětlení: 

```cpp 
int yearofbirth = 1995; 

float averageGrade = 4.5; 
``` 

Float proměná může narozdíl od int proměné obsahovat i desetiná čísla 

```cpp 
char gender = "f"; 
``` 

Vytvoři proměnou s formátem character (písmeno) 

```cpp 
double accBalance = 454315646; 
``` 

Vytvoří proměnou s alokovanou dvojnásobnou pamětí —> tudíž 8 bitů —> dokáže udržet více dat 

```cpp 
cout << "size of int is: " << sizeof(int) << " bytes" << endl; // 4 bytes 
cout << "size of double is: " << sizeof(double) << "bytes" << endl; // 8 bytes 
``` 

Vypíší do konzole velikost proměné int a double v bytech 

```cpp 
cout << int("a") << endl; 
cout << char("97") << endl; 
``` 

Vrátí ASCII číslo písmena a, vrátí písmeno s číslem 97 v ASCII soustavě
