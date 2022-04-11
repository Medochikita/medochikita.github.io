- [Home](/cplusplus/home)

# Intro to classes 

Datum: 10/04/2022 
Tags: C++ 
Téma: Classes 

Intro do Classu v C++ 

```cpp 
//Song.h 

#include <string> 

class Song { 

std::string title; //objekt v této classe může mít atribut název 
std::string artist; 

public: 
void add_title(std::string new_title); //funkce která přidá nový název, deklarovaná v song.cpp 
std::string get_title(); //funkce na dostání názvu, deklarovaná v song.cpp 
void add_artist(std::string new_artist); 
std::string get_artist(); 

}; 
``` 

```cpp 
//Song.cpp 

#include "Song.h" 

void Song::add_title(std::string new_title) { 

title = new_title; //deklarace samotných funkcí v Classe Song 

} 

std::string Song::get_title() { 

return title; 

} 

void Song::add_artist(std::string new_artist) { 

artist = new_artist; 

} 

std::string Song::get_artist() { 

return artist; 

} 
``` 

Main file main.cpp 

```cpp 
//main.cpp 

#include <iostream> 
#include "song.h" 

int main() 
{ 

Song electric_relaxation; 
electric_relaxation.add_artist("A Tribe Called Quest"); 

std::cout << electric_relaxation.get_artist(); // A Tribe Called Quest 

} 
```
