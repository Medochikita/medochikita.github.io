code here: <br>
```
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

}; ``` <br>
Hello
