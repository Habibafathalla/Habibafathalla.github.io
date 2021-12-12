1.	Const keyword usages:

1.1	Constant Variables

1.2	Const Keyword With Pointer Variables:

1.2.1	Pointer variable points to a const value

1.2.2	const pointer variable points to the value

1.2.3	const pointer pointing to a const variable

1.3	const Function Arguments and Return types

1.4	Defining Class Object as const

1.5	Const class member’s function:

2.	& operator usages:

2.1	Address operator

2.2	Logical And

2.3	Bitwise AND

2.4	Bitwise AND Assignment


1.	Const keyword usages:

The keyword “const” can be used with any variables ,pointers ,method() and objects from a class ,and once the keyword “const” is attached to them ,their values can not be changed or modified 

1.1Constant Variables: 

To have a const variable, it has to be initialized at the time of assignment when they are declared and not at any place in the program  

C++ code for constant variable:

```
int main(){
//const intx; compile time error (CTE)
//X=2;     (CTE)
const int x=2;
}
```
(CTE) cause we can’t declare const variable without initialize it

```
int main(){
const int x=2;
const int y = x + 3;
 // x++; (CTE)
}
```
(CTE) cause we can’t change the value of const variable


1.2	Const Keyword With Pointer Variables

We can use the keyword const with pointer in three ways 

1.2.1	Pointer variable points to a const value:
the pointer is pointing to a const variable.

Syntax: 
```
const data_type* var_name;
```
C++ code for Pointer variable points to a  const value: 

```
int main(){
    int x{ 10 }; 
    const int* i = &x;
    x = 9;   //NO (CTE)
    // *i = 6 ;    (CTE)
```
Note: (CTE) cause once ptr(*i) is pointing at const int-type memory location and it can’t be modified 

1.2.2	const pointer variable points to the value:
we can not change the type of the pointer but surly we can change the the value of the variable 

 Syntax:

```
data_type* const var_name;
```
C++ code for const Pointer variable points to a value: 

```
Int main(){
	int x = 6;
	int z = 9;
	char y = 'B';
	char p = 'E';
	int* const i = &x;      // const pointer(i) pointing  to the var x's location
	char* const j = &y;
	*i = 10;        // No CTE error
    *j = 'D';       // No CTE error
	// *i = &z;        // CTE
	// *j = &p;         // CTE
}
```
Notes: Not (CTE) cause the variables which is pointed at are not const and can be changed without errors while (CTE) will appear cause the pointer itself is const this means that the values are stored in const locations

1.2.3	const pointer pointing to a const variable:

Syntax:
```
const data_type* const variable_name; 
```
```
int main()
{
    int x{ 4};
    const int* const i = &x;
   
    // *i=16;  (CTE)}
```
Note: (CTE) cause once const ptr(*i) is assigned to value,it can not be modified or changed 
1.3	const Function Arguments and Return types
we can declare a function() and it’s return type as const which can’t be changed throughout the program and any trail will lead to CTE

```
void foo(const int x)
{
  // x++   const value  CTE
}
const int foo(int z)
{
    z++;
    return z;
}
```
Note that passing const value to a non const function will case a compile time error
But we can pass const or non const value to a build in datatyps 

Examples for the note:

```
int foo(int*x)
{
    return *x;
}
 int main()
{
    int y = 8;
    const int* x = &z   
 cout << foo(x);     //CTE
}
```
```
const int S()
{
    return 1;
}
int main()
{
    const int j = S();
    int k = S();
}
```

1.4	Defining Class Object as const

As we cane declare functions and its members as const we can also declare objects of a class as const which cannot be modified through the program and it needs to be initialized when declared by the help of constructors 

Syntax:
```
const Class_Name Object_name;
```
Example:
```
const foo object; 
const foo r(30);
```

1.5	Const class member’s function:

We cannot change or modify a const member function 
Syntax

```
return_type function_name() const;
```
Code Example:

```
int fun() const  // constant function
    { 
        /* 
           we can do anything but will not
            modify any data members
        */
        cout << "Fun has left the Base";
    }
```

2.	& operator usages:

4.1	Address operator

It is used to get the address or the reference of the value 

```
int x;
int &ptr = x;       //  ptr reference to an integer x
```
2.2	Logical And
Logic operators mainly take iput Boolean values and return also Boolean values as output
&& represents AND gait which returen true if both inputs are ture ,else it return false

2.3	Bitwise AND
Bitwise operators perform the operation of the inputs by converting them to binary and preform the operation the represent the output result as integers once again 
(x & z) it the both inputs are set to bit then it set the result to bit too 

Example: 
Assume x=42      z=27
              X=00101010     z=00011011
The x&z=000010010=10(in decimal)

2.4	Bitwise AND Assignment  (&=)

 Example : x=x&=z  this means that it preforme (x&z)and then store the output in x 
