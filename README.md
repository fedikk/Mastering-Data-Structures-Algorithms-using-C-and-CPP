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
/* it takes 4 Bytes*/
int length;
/* it takes 4 Bytes*/
int width;   
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
# Pointers 
data variable       int a=10;
address variables   int *p; 
p= &a; 
printf("%d",a);
printf("%d",*p);

to allocate memory in the **Heap memory Section**

```C

#include<stdlib.h>
int main()
{
int *p;
/*this will allocate 10 Bytes in the heap memory in C language*/
p=(int *)malloc(7*sizeof(int));
/*this will allocate 10 Bytes in the heap memory in C++ language*/
p= new int[8]
}

```

![image](https://github.com/user-attachments/assets/e78efa4e-d118-4aef-a4ee-2772fcf6ad68)

you should also delete the memory used after we finish using it 

```C

#include<stdlib.h>
int main()
{
int *p;
p=(int *)malloc(7*sizeof(int));

delete [] p; /*used ic C++ Language*/
free(p);     /*used in C   Language*/
}

```

```C
#include <iostream>
using namespace std;
struct Rectangle {
    int len;
    int width;
};
int main() {
    int *p1;
    char *p2;
    float *p3;
    double *p4;
    struct Rectangle *p5;
    cout<<sizeof(p1)<<endl;
    cout<<sizeof(p2)<<endl;
    cout<<sizeof(p3)<<endl;
    cout<<sizeof(p4)<<endl;
    cout<<sizeof(p5)<<endl;
    return 0; 
}

```
![image](https://github.com/user-attachments/assets/bf57a165-5365-47fe-90fb-65d1116ba9c9)

# Reference in C++ 

```C++
#include <iostream>
using namespace std;
int main() {
   int a=4;
   /*
   int r;   This is a variable to store integer 
   int *r;  This is a pointer to store the address
   int &r;  This is a reference and you must initialized
   */
   int &r=a;
 
}

```
![image](https://github.com/user-attachments/assets/5e7cb0ea-55e8-4e29-800d-d9ecaca3c2f7)


# Pointer to Structure

```C++
#include <iostream>
using namespace std;
struct Rectangle {
    int len;
    int width;
};
int main() {
    struct Rectangle r={20,21};
    struct Rectangle *p=&r;
    r.len=4;
    cout<<"("<<r.len<<","<<r.width<<")"<<endl;
    p->len=10; //(*p).len = 10;
    cout<<"("<<r.len<<","<<r.width<<")"<<endl;
}
```

```
(4,21)
(10,21)
```

```C++
#include <iostream>
using namespace std;
struct Rectangle {
    int len;
    int width;
};
int main() {
    struct Rectangle *p;
    p=(struct Rectangle *)malloc(sizeof(struct Rectangle));
    p->len=55;
    p->width=7;
    cout<<"("<<p->len<<","<<p->width<<")"<<endl;
    free(p);
}
```

# Function 

for paramater passing in C : 
  - Pass by value
  - Pass by adress

For C++: 
  - Pass by reference
  - Pass by value
  - Pass by adress

```C++
#include <iostream>
using namespace std;
int add(int a , int b)
{
  int c ;
  c = a+b;
  return c;
}
int main() {
   int x,y,z;
   x=15;
   y=46;
   z= add(x,y);
   printf("sum = %d",z);
}
```
# Parameter passing methods
