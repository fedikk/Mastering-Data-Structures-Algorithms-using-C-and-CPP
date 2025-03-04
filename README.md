# Mastering Data Structure & Algorithms using C and C++

# Essentiel C and C++ Concepts 

## Arrays Basics 

how to declare an array : int A[5] ;
- A[0]=12
- A[1]=54
- A[2]=20
-  A -> |12|54|20| 

![image](https://github.com/user-attachments/assets/d9a673d2-97fd-4ca1-9113-f860ad44e851)

To print the value of an element in **C Language**: 

```C
int main(){
int A[5]={1,2,3,4,5};
for (int i=0; i<5;i++){
  printf("%d",A[i]);
}
}
```

## Practice Arrays 

![image](https://github.com/user-attachments/assets/0c906dc4-dbc6-420e-8747-2b722ae16c65)

if i assign A[n]={0} all the array will be filled of zeros 

![image](https://github.com/user-attachments/assets/5d4305d1-a058-48eb-b281-10df5d298ae3)

how to parcours an Array : 

```C
#include <stdio.h>

int main() {
    int A[5]={0};
    for (int i=0;i<5;i++){
        printf("%d|",A[i]);
    }
    return 0;
}
```

In C++ you can also do this : 

```C
#include <iostream>

int main() {
    int A[5]={2,3,1,4,5};
    for (int i:A){
        printf("%d|",i);
    }
    return 0;
}
```

## Structures 

if you want to define a structure 

```C
Struct Rectangle
{
int length;  /* it takes 4 Bytes*/
int width;   /* it takes 4 Bytes*/
/*Our Structure is 8 Bytes Memory */
}
```

how to declare a variable of the structure type 

```C

int main()
{
struct Rectangle r;         /*Declaration*/
struct Rectangle r1={10,5}; /*Declaration with initialisation*/
r1.length = 12;
r.width   = 10;
printf("Area of Rectangle = %d", r1.length*r1.width); 
}

```

Let's write now a **Complex Number**: 

```C
Struct ComplexNumber
{
/* complex number = a + i * b  */
int real;  /* it takes 4 Bytes*/
int img;   /* it takes 4 Bytes*/
}
```


```C
Struct Student 
{
char name[25] ;
char LastName[25];
int StudentID;
char Departement[25];
char addr[50];
int phonenumber;
}
```

