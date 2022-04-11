- [Home](/cplusplus/home)

# bmi caltulator 

Datum: 05/04/2022 
Tags: C++ 
Téma: if statement 

```cpp 
#include <iostream> 
using namespace std; 

int main() 
{ 

float height, weight; 

cout << "Enter body weight in kgs: "; 
cin >> weight; 

cout << "Enter your heaight in cms: "; 
cin >> height; 

height = height / 100; 

float bmi; 
bmi = weight / (height * height); 

if (bmi < 18.5) 
{ 
cout << "your underweight and your bmi is " << bmi << endl; 
} 
else if (bmi > 25) 
{ 
cout << "your overweight and your bmi is " << bmi << endl; 
} 
else 
{ 
cout << "your weight is fine and your bmi is " << bmi << endl; 
} 

return 0; 
} 
```
