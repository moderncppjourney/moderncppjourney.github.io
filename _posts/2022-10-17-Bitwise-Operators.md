---
layout: post
title: Bitwise Opertors
tags: basics bitwise
categories: cpp basics
---
Let me explain Bitwise Operators in detail

There is library available in c++ called bitset, which has a lot of bit manipulation functions.
In below program bitset helps to print in bits `std::bitset<8>(data)`, instead of 8 if we give 16 it will print 16 bits.

```cpp
#include <iostream>
#include <bitset>


int main(){

    unsigned short int data {15};

    std::cout << "data (dec) : " <<std::showbase <<  std::dec << data << std::endl;
    std::cout << "data (oct) : " <<std::showbase <<  std::oct << data << std::endl;
    std::cout << "data (hex) : " <<std::showbase <<  std::hex << data << std::endl;
    std::cout << "data (bin) : " << std::bitset<8>(data) << std::endl;
   
    return 0;
}
```
output will be

```bash
data (dec) : 15
data (oct) : 017
data (hex) : 0xf
data (bin) : 00001111
```

## Shift Operators

<< - left shift operator

<< - right shift operator

```cpp
#include <iostream>
#include <bitset>


int main(){

	unsigned short int value {0x0f0u};
	
    std::cout << " Original value : " << std::bitset<12>(value) 
    << ", dec : " << value << std::endl;

    //Shift left by one bit
    auto left_value = static_cast<unsigned short int>(value << 1);
    std::cout << " Shifted  value : " << std::bitset<12>(left_value) 
    << ", dec : " << left_value << std::endl;

    //Shift right by one bit
    auto right_value = static_cast<unsigned short int>(value >> 1);
    std::cout << " Shifted  value : " << std::bitset<12>(right_value) 
    << ", dec : " << right_value << std::endl;

   
    return 0;
}
```
output will be

```bash
Size of short int 2
Original value : 000011110000, dec : 240
Shifted  value : 000111100000, dec : 480
Shifted  value : 000001111000, dec : 120
```

**left shift operator (<<) is equal to multiplying by 2<sup>n</sup>**. Where n is no of times we are shifting.
So if we are shifting 3 times then

**value << 3 == value * (2<sup>3</sup>)**


**right shift operator (>>) is equal to dividing by 2<sup>n</sup>**. Where n is no of times we are shifting.
So if we are shifting 3 times then

**value >> 3 == value / (2<sup>3</sup>)**

```cpp
#include <iostream>
#include <bitset>


int main(){

	unsigned short int value {0x0f0u};

	std::cout << "Size of short int " << sizeof(short int) <<  std::endl;//  16 bits
	
    std::cout << "     Original value : " << std::bitset<12>(value) 
    << ", dec : " << value << std::endl;

    //Shift left by One bit
    auto left_value = static_cast<unsigned short int>(value << 1);
    std::cout << "Left Shifted  value : " << std::bitset<12>(left_value) 
    << ", dec : " << left_value << std::endl;
    
    //Shift left by One bit
    left_value = static_cast<unsigned short int>(left_value << 1);
    std::cout << "Left Shifted  value : " << std::bitset<12>(left_value) 
    << ", dec : " << left_value << std::endl;
    
    //Shift left by One bit
    left_value = static_cast<unsigned short int>(left_value << 1);
    std::cout << "Left Shifted  value : " << std::bitset<12>(left_value) 
    << ", dec : " << left_value << std::endl;
    
    //Shift left by One bit
    left_value = static_cast<unsigned short int>(left_value << 1);
    std::cout << "Left Shifted  value : " << std::bitset<12>(left_value) 
    << ", dec : " << left_value << std::endl;

    std::cout << "     Original value : " << std::bitset<12>(value) 
    << ", dec : " << value << std::endl;

    //Shift right by one bit
    auto right_value = static_cast<unsigned short int>(value >> 1);
    std::cout << "Right Shifted value : " << std::bitset<12>(right_value) 
    << ", dec : " << right_value << std::endl;

    //Shift right by one bit
    right_value = static_cast<unsigned short int>(right_value >> 1);
    std::cout << "Right Shifted value : " << std::bitset<12>(right_value) 
    << ", dec : " << right_value << std::endl;

    //Shift right by one bit
    right_value = static_cast<unsigned short int>(right_value >> 1);
    std::cout << "Right Shifted value : " << std::bitset<12>(right_value) 
    << ", dec : " << right_value << std::endl;

    //Shift right by one bit
    right_value = static_cast<unsigned short int>(right_value >> 1);
    std::cout << "Right Shifted value : " << std::bitset<12>(right_value) 
    << ", dec : " << right_value << std::endl;

   
    return 0;
}
```
output will be

```bash
Size of short int 2
     Original value : 000011110000, dec : 240
Left Shifted  value : 000111100000, dec : 480 - (val * 2)
Left Shifted  value : 001111000000, dec : 960 - (val * 2)
Left Shifted  value : 011110000000, dec : 1920 - (val * 2)
Left Shifted  value : 111100000000, dec : 3840 - (val * 2)
     Original value : 000011110000, dec : 240
Right Shifted value : 000001111000, dec : 120 - (val / 2)
Right Shifted value : 000000111100, dec : 60 - (val / 2)
Right Shifted value : 000000011110, dec : 30 - (val / 2)
Right Shifted value : 000000001111, dec : 15 - (val / 2)
```
