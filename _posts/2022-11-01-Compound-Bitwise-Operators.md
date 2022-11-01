---
layout: post
title: Compound Bitwise Opertors
tags: basics bitwise
categories: cpp basics
---

Compound Bitwise Opertors explained

```bash
Shift Left  -  (sandbox_var <<= 2)
Shift Right -  (sandbox_var >>= 4)
OR          -  (sandbox_var |= 0b00001111)
AND         -  (sandbox_var &= 0b000001100)
XOR         -  (sandbox_var ^= 0b00000011)
```

```cpp
#include <iostream>
#include <iomanip>
#include <bitset>


int main(){

	const int COLUMN_WIDTH {20};

	std::cout << std::endl;
	std::cout << "Compound bitwise assignment operators" << std::endl;
	
	unsigned char sandbox_var{0b00110100}; // 8 bits : positive numbers only
	
	//Print out initial value
	std::cout << std::endl;
	std::cout << "Initial value :  " << std::endl;
    std::cout << std::setw(COLUMN_WIDTH) << "sandbox_var : "
		<< std::setw(COLUMN_WIDTH) << std::bitset<8>(sandbox_var) << std::endl;
    std::cout << std::endl;
	
	//Compound left shift
	std::cout << std::endl;
	std::cout << "Shift left 2 bit positions in place :  (sandbox_var <<= 2)" << std::endl;
	sandbox_var <<= 2;
    std::cout << std::setw(COLUMN_WIDTH) << "sandbox_var : "
		<< std::setw(COLUMN_WIDTH) << std::bitset<8>(sandbox_var) << std::endl;
    std::cout << std::endl;


    //Compound right shift
	std::cout << std::endl;
	std::cout << "Shift right 4 bit positions in place :  (sandbox_var >>= 4)" << std::endl;
	sandbox_var >>= 4;
    std::cout << std::setw(COLUMN_WIDTH) << "sandbox_var : "
		<< std::setw(COLUMN_WIDTH) << std::bitset<8>(sandbox_var) << std::endl;
    std::cout << std::endl;

	//Compound OR with 0000 0010 to have all lower 4 bits turned on 
	std::cout << std::endl;
	std::cout << "Compound OR with 0000 0010 :  (sandbox_var |= 0b00001111)" << std::endl;
	sandbox_var |= 0b00001111;
    std::cout << std::setw(COLUMN_WIDTH) << "sandbox_var : "
		<< std::setw(COLUMN_WIDTH) << std::bitset<8>(sandbox_var) << std::endl;
    std::cout << std::endl;


	//Compound AND with 0000 1100 to turn off the 2 lowest bits
	std::cout << std::endl;
	std::cout << "Compound AND with 0000 1100 :  (sandbox_var &= 0b000001100)" << std::endl;
	sandbox_var &= 0b000001100;
    std::cout << std::setw(COLUMN_WIDTH) << "sandbox_var : "
		<< std::setw(COLUMN_WIDTH) << std::bitset<8>(sandbox_var) << std::endl;
    std::cout << std::endl;


	//XOR with 00000011 to turn on the 4 lowest bits again
	std::cout << std::endl;
	std::cout << "Compound XOR with 0000 0011 :  (sandbox_var ^= 0b00000011)" << std::endl;
	sandbox_var ^= 0b00000011;
    std::cout << std::setw(COLUMN_WIDTH) << "sandbox_var : "
		<< std::setw(COLUMN_WIDTH) << std::bitset<8>(sandbox_var) << std::endl;
    std::cout << std::endl;
	
    
    return 0;
}

```

output

```bash

Compound bitwise assignment operators

Initial value :  
      sandbox_var :             00110100


Shift left 2 bit positions in place :  (sandbox_var <<= 2)
      sandbox_var :             11010000


Shift right 4 bit positions in place :  (sandbox_var >>= 4)
      sandbox_var :             00001101


Compound OR with 0000 0010 :  (sandbox_var |= 0b00001111)
      sandbox_var :             00001111


Compound AND with 0000 1100 :  (sandbox_var &= 0b000001100)
      sandbox_var :             00001100


Compound XOR with 0000 0011 :  (sandbox_var ^= 0b00000011)
      sandbox_var :             00001111


```


