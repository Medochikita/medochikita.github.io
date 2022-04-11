- [Home](/cplusplus/home)

# Základní program 

Datum: 04/04/2022 <br>
Tags: C++ <br>
Téma: Základní program do konzole <br>

# Den 1. v C++ 

### Základní program v C++ 

```cpp 
#include <iostream> 
using namespace std; 

int main() 
{ 
cout << "Salary: "; 

float salary; 
cin >> salary; 
float salary12 = salary / 12; 

cout << "your salary per month is: " << salary12 << endl; 

cout << "In 10 years you will earn: " << salary * 10 << endl; 

return 0; 
} 
``` 

### Vysvětlení: 

```cpp 
int main() 
{ 

return 0; 
} 
``` 

Funkce která se spustí při spuštění programu 

```cpp 
cout << "Salary: "; 
``` 

Napíše do konzole text “Salary: “ 

```cpp 
float salary; 
``` 

Vytvoří proměnou s názvem salary s formátem float 

```cpp 
cin >> salary; 
``` 

Bude očekávat vstup do konzole a přiřadí tuto hodnotu následně proměné salary 

```cpp 
float salary12 = salary / 12; 
``` 

Vytvoří stejnou proměnou s formátem float s názvem salary12 do které přiřadí hodnotu z proměné salary vydělenou 12 

```cpp 
cout << "your salary per month is: " << salary12 << endl; 
``` 

Vypíše do konzole text za který přidá hodnotu z promněné salary12, endl ukončí řádek 

```cpp 
cout << "In 10 years you will earn: " << salary * 10 << endl; 
``` 

Vypíše do konzole text a za něj přidá proměnou salary vynásobenou 10x
