# Arrays

Datum: 14/04/2022
Tags: C++
Téma: Arrays

# Arrays

```cpp
#include <iostream>

int main()
{
		int prime[5]{ 2, 3, 5, 7, 11 }; // like this or:

    int prime[5]; // hold the first 5 prime numbers
    prime[0] = 2; // The first element has index 0
    prime[1] = 3;
    prime[2] = 5;
    prime[3] = 7;
    prime[4] = 11; // The last element has index 4 (array length-1)

    std::cout << "The lowest prime number is: " << prime[0] << '\n';
    std::cout << "The sum of the first 5 primes is: " << prime[0] + prime[1] + prime[2] + prime[3] + prime[4] << '\n';

		double batteryLifeInHours[3]{}; // allocate 3 doubles
    batteryLifeInHours[0] = 2.0;
    batteryLifeInHours[1] = 3.0;
    batteryLifeInHours[2] = 4.3;

    return 0;
}
```

---

```cpp
#include <iostream>

int main()
{
    int array[5]{ 7, 4, 5 }; // only initialize first 3 elements

    std::cout << array[0] << '\n';
    std::cout << array[1] << '\n';
    std::cout << array[2] << '\n';
    std::cout << array[3] << '\n';
    std::cout << array[4] << '\n';

    return 0;
}
```

This will output 7, 4, 5, 0, 0, because the last two elements werent initialized

```cpp
// Initialize all elements to 0
int array[5]{ };

// Initialize all elements to 0.0
double array[5]{ };
```

All elements are set to 0 in this case, whereas here:

```cpp
// uninitialized
int array[5];

// uninitialized
double array[5];
```

Elements are not set to any value. Its better to initialize arrays than leave them uninitialized

```cpp
int array[5]{ 0, 1, 2, 3, 4 }; // explicitly define the length of the array
int array[]{ 0, 1, 2, 3, 4 }; // let the initializer list set length of the array
```

In the first line we set the lenght of the array, in the second line the program will set the lenght of the array based on how many elements have we passed to it

Big problem is that we may know whats in the array on some index, but we dont know what does the index mean. This can be solved with enumerator:

```cpp
enum StudentNames
{
    kenny, // 0
    kyle, // 1
    stan, // 2
    butters, // 3
    cartman, // 4
    max_students // 5
};

int main()
{
    int testScores[max_students]{}; // allocate 5 integers
    testScores[stan] = 76;

    return 0;
}
```

---

## Passing array to a function

```cpp
#include <iostream>

void passValue(int value) // value is a copy of the argument
{
    value = 99; // so changing it here won't change the value of the argument
}

void passArray(int prime[5]) // prime is the actual array
{
    prime[0] = 11; // so changing it here will change the original argument!
    prime[1] = 7;
    prime[2] = 5;
    prime[3] = 3;
    prime[4] = 2;
}

int main()
{
    int value{ 1 };
    std::cout << "before passValue: " << value << '\n';
    passValue(value);
    std::cout << "after passValue: " << value << '\n';

    int prime[5]{ 2, 3, 5, 7, 11 };
    std::cout << "before passArray: " << prime[0] << " " << prime[1] << " " << prime[2] << " " << prime[3] << " " << prime[4] << '\n';
    passArray(prime);
    std::cout << "after passArray: " << prime[0] << " " << prime[1] << " " << prime[2] << " " << prime[3] << " " << prime[4] << '\n';

    return 0;
}
```

When we pass a value to a function, it will just do a copy of it, because we are passing by value, whereas when we pass an array, we pass the original array, not just its copy. So when we in this case try to do the same thing with the array as with the value, the array changes and the value dont.

Here is the output:

```
before passValue: 1
after passValue: 1
before passArray: 2 3 5 7 11
after passArray: 11 7 5 3 2
```

---

## Lenght of array

```cpp
#include <iostream>
#include <iterator> // for std::size

int main()
{
    int array[]{ 1, 1, 2, 3, 5, 8, 13, 21 };
    std::cout << "The array has: " << std::size(array) << " elements\n";

    return 0;
}
```

Output will be:

```
The array has: 8 elements
```