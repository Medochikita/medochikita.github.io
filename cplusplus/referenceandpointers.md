- [Home](/cplusplus/home)

# Pass by reference

Datum: 11/04/2022 <br>
Tags: C++ <br>
Téma: Functions and pointers <br>

# Passing by value and passing by reference

```cpp
#include <iostream>

int triple(int &i) {

  i = i * 3;
  
  return i;

}

int main() {
  
  int num = 1;
  
  std::cout << triple(num) << "\n"; // 3
  std::cout << triple(num) << "\n"; // 9

}
```

To the triple function we pass the variable **by reference**, that means, that when we triple the value of i, we triple the value in the memory, which means that it will work even outside of the function

```cpp
#include <iostream>

int triple(int i) {

  i = i * 3;
  
  return i;

}

int main() {
  
  int num = 1;
  
  std::cout << triple(num) << "\n"; // 3
  std::cout << triple(num) << "\n"; // 3

}
```

Now we removed the & out of the argument we are passing just the value of the variable. That means, that on the first run we pass value 1 and we get 3, but on the second run, we also pass value 1, and get 3, as the value of the variable num havent changed. This is called passing **by value**