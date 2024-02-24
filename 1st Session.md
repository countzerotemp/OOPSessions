# Titles ...



- [what are types of PCs Storage?](#What-are-types-of-PCs-Storage?)
- [what is RAM?](#what-is-RAM?)
- [what is Hexadecimal system?](#what-is-Hexadecimal-system?)
- [Reference, Dereference, &Pointer-Definitions, Examples?](##reference-dereference-pointer-definitions-examples)
- [why-Dereferencing-&-why-it-is-related-to-Pointer?-About-Casting!](#why-dereferencing--why-it-is-related-to-pointer-about-casting)
- [Operations-on-pointer-value](##operations-on-pointer-value)
- [Operations-on-dereferenced-pointer-value](##operations-on-dereferenced-pointer-value)
- [Structure-Definition,-And-sideways-glance](##structure-definition-and-sideways-glance)
- [what-is-OOP?,-And-its-advantages](##what-is-oop-and-its-advantages)
- [what-is-the-Class,-And-what-is-the-origin-of-it?](##what-is-the-class-and-what-is-the-origin-of-it)
- [Class-is-the-Coach,-and-Object-is-the-Player](##class-is-the-coach-and-object-is-the-player)

----







## what are types of PCs Storage?

- primary storage (RAM) - Involatile - fast 
- secondary storage (HDD, SSD) - volatile - slower



## what is RAM?

- it looks like apartment numbers



## what is Hexadecimal system?

- it is a number of an apartment



## Reference, Dereference, &Pointer Definitions, Examples?

- Reference is a  datatype 

- variables' nickname

- ref. Conditions 

  

  `ex`

  ```c++
   string name = "Ali";
   string &first_name = name; //(Must be done here)
  
      // printing (name) or (first_name) lead to (Ali)
  
  ```



- Pointer is a datatype 

- the house of other variables

- pointer conditions

  

  `ex`

  ```c++
  char letter = 'A';
  char *my_pointer;
  myPointer = &letter; // (No need to make assignemt operation during declaration)
  ```

  

- Dereference is an operation

- gets the variable value inside the pointer

  

  `ex`

  ```c++
  char letter = 'A';
  char *my_pointer;
  myPointer = &letter; // (No need to make assignemt operation during declaration)
  
  std::cout << my_pointer << '\n'; // prints pointer value
  std::cout << *my_pointer << '\n'; // prints variable value inside the pointer
  
  ```



## why Dereferencing & why it is related to Pointer? (About Casting!)

- at real dereferencing operation is used for more advanced purposes

- one of those purposes is (casting operation related with pointers)

- dereferencing uses to specify how many bytes will it invoke during access variable address

  `ex`

  ```c++
  int number = 3;	// 11000000 00000000 00000000 00000000
  int *my_pointer = &number; 
  char *my_pointer2 = (char*)my_pointer;
  
  cout << (int)*my_pointer2 << '\n'; // dereferencing, then casting
  ```
  



## Operations on pointer value

- increasing & decreasing on a pointer value

  `ex`

  ```c++
  my_pointer2++;	// increasing address by a byte
  my_pointer2 -= 1; // my_pointer2 = my_pointer2 - 2
  ```

  

## Operations on dereferenced-pointer value

- increasing & decreasing on the dereferenced-value

  `ex`

  ```c++
  std::cout << (int)*my_pointer2 << '\n'; // prints 3
  my_pointer2++;
  std::cout << (int)*my_pointer2 << '\n'; // prints 0 (the second byte)
  ```



## Structure Definition, And sideways glance

- structure is a user-defined datatype

  `ex`

  ```c++
  struct my_datatype
  {
      int built_in1;
      char built_in2;
  };
  ```

- structure operations

  

## what is OOP?, And its advantages

- new efficient way for handling code
- no OOP, no Independency



## what is the Class, And what is the origin of it?

- Class is your architecture
- Class is a conditioned-structure

`ex`

```c++
class class1
{
private:
    int properity1;
    char properity2;
public:
    void operatoin1()
    {
        cout << member1 << " " << member2 << '\n';
    }
};
```



## Class is the Coach, and Object is the Player

- the object is an instance from the class

`ex`

```c++
int main()
{
    class1 object1;
}
```
