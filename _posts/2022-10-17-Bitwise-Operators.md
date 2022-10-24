---
layout: post
title: Bitwise Opertors
tags: basics bitwise
categories: cpp basics
---
Let me explain Bitwise Operators in detail

There is libraru available in c++ called bitset, which has a lot of bit manipulation functions.
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
