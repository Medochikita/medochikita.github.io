- [Home](/cplusplus/home)

# Pointers základy 

Datum: 05/04/2022 
Tags: C++ 
Téma: memory pointers 

```cpp 
#include <iostream> 
using namespace std; 

int main() 
{ 

int n = 5; 

cout << &n << endl; //000000A9E550F784 adresa této promněné n 

int* pointer = &n; 

cout << pointer << endl; //000000A9E550F784 v proměné pointer je uložena adresa proměné n 

cout << *pointer << endl; //5 --> ptáme se jaká je hodnota na adrese kterou má pointer uloženou 

return 0; 
} 
``` 

```cpp 
cout << &n << endl; 
``` 

Vypíše adresu proměné n 

```cpp 
int* pointer = &n 
``` 

Připíše do proměné pointer adresu proměné n 

```cpp 
cout << *pointer << endl; 
``` 

Ptáme se jaká hodnota je na akresd kterou má v sobě proměná pointer 

--- 

```cpp 
#include <iostream> 
using namespace std; 

void print(void* pointer, char type) { //potřebuje pointer na adresu a typ co je to za typ 
switch (type) 
{ 
case 'i': 
cout << *((int*)pointer) << endl; break; // pro int 
case 'c': 
cout << *((char*)pointer) << endl; break; // pro char 
} 
} 

int main() 
{ 

int n = 5; 
char letter = 'c'; 

print(&n, 'i'); 
print(&letter, 'c'); //mohu tam passnout jakýkoli pointer ale musim specifikovat co to je 

return 0; 
} 
```
