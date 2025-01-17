---
layout: post
title: Logical Bitwise Opertors
tags: basics bitwise
categories: cpp basics
---

Logical Bitwise Opertors explained

![image](https://user-images.githubusercontent.com/265046/199296600-4f4d3452-709d-41f5-b881-3dd27175f98d.png)


![image](https://user-images.githubusercontent.com/265046/199293199-e2df149f-ede7-4c08-946b-0be970e737d0.png)


```cpp

#include <iostream>
#include <iomanip>
#include <bitset>

int main(){

    int COLUMN_WIDTH {20};
    unsigned char value1 {0x3}; // 0000 0011
    unsigned char value2 {0x5}; // 0000 0101
	

    std::cout << std::setw(COLUMN_WIDTH) << "value1 : " 
		<< std::setw(COLUMN_WIDTH) << std::bitset<8>(value1) << std::endl; 
		
	std::cout << std::setw(COLUMN_WIDTH) << "value2 : "
		<< std::setw(COLUMN_WIDTH) << std::bitset<8>(value2) << std::endl;
    
	//AND
	std::cout << std::endl;
	std::cout << "Bitwise AND :  " << std::endl;
    std::cout << std::setw(COLUMN_WIDTH) << "value1 & value2 : "
		<< std::setw(COLUMN_WIDTH) << std::bitset<8>(value1 & value2) << std::endl;
    std::cout << std::endl;

	//OR
	std::cout << std::endl;
	std::cout << "Bitwise OR :  " << std::endl;
    std::cout << std::setw(COLUMN_WIDTH) << "value1 | value2 : "
		<< std::setw(COLUMN_WIDTH) << std::bitset<8>(value1 | value2) << std::endl;
    std::cout << std::endl;


    //NOT
	std::cout << std::endl;
    std::cout << "Bitwise NOT " << std::endl;
	
    std::cout << std::setw(COLUMN_WIDTH) << "~value1 : "
		<< std::setw(COLUMN_WIDTH) <<  std::bitset<8>(~value1) << std::endl;
		
    std::cout << std::setw(COLUMN_WIDTH) << "~value2 : "
		<< std::setw(COLUMN_WIDTH) << std::bitset<8>(~value2) << std::endl;
		
    std::cout << std::setw(COLUMN_WIDTH) << "~01011001 : "
		<< std::setw(COLUMN_WIDTH) << std::bitset<8>(~0b01011001) << std::endl;//Using bin literal
		
    std::cout << std::setw(COLUMN_WIDTH) << "~0x59 : "
		<< std::setw(COLUMN_WIDTH) << std::bitset<8>(~0x59) << std::endl;//Using hex literal
    std::cout << std::endl; 


	//XOR
	std::cout << std::endl;
	std::cout << "Bitwise XOR :  " << std::endl;
    std::cout << std::setw(COLUMN_WIDTH) << "value1 ^ value2 : "
		<< std::setw(COLUMN_WIDTH) << std::bitset<8>(value1 ^ value2) << std::endl;
    std::cout << std::endl;
   
    return 0;
}

```

output


```bash
           value1 :             00000011
           value2 :             00000101

Bitwise AND :  
  value1 & value2 :             00000001


Bitwise OR :  
  value1 | value2 :             00000111


Bitwise NOT 
          ~value1 :             11111100
          ~value2 :             11111010
        ~01011001 :             10100110
            ~0x59 :             10100110


Bitwise XOR :  
  value1 ^ value2 :             00000110


```
