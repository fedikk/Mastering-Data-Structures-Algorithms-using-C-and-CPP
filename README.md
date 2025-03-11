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

```C
/*The formel parameter will be modified*/
void swap(int x,int y)
{
int temp;
temp=x;
x=y;
y=temp;
}

int main(){
int a=10,b=20;
swap(a,b);
printf("%d %d",a,b);

}

10,20 
```

In The **pass by value** the original parmaeter value ont change 
we work on a copy of it.

- We generally use the passing parameter when the function should return a type

# Call by Address
  
Any change inside the function will modify the actual parameters 
Let's learn how to **write Call by Address** and how **it works**

```C
/*The formel parameter will be modified*/
void swap(int *x,int* y)
{
int temp;
temp=*x;
*x=*y;
*y=temp;
}

int main(){
int a=10,b=20;
swap(&a,&b);
printf("%d %d",a,b);
}

```

# Call by Reference ( Only in C++ ) 

Let's learn how to **write Call by Reference** and how **it works**

```C
/* x will become a reference to a and y will be a reference to b */
void swap(int &x,int &y)
{
int temp;
temp=x;
x=y;
y=temp;
}

int main(){
int a=10,b=20;
swap(a,b);
printf("%d %d",a,b);
}

```

<quote>
Dont use Call by reference to heavy functions and Complex logic .
</quote>

# Array as a Parameter 

```C
/* We should put the bruckers [] */
/*void fun (int *A,int n)*/
void fun (int A[],int n)
{
  /* I can modify the value of an element */
  A[0]=44; 
  for (int i=0;i<n;i++)
  {
    printf("%d",A[i]);
  }
}

int main(){
  int A[3]={2,4,6};
  fun(A,3);
}

```

with C++: 

```C++
#include <iostream>


void fun (int A[])
{
  for (int i=0;i<3;i++)
  {
    printf("%d",A[i]);
  }
  
}

int main(){
  int A[3]={2,4,6};
  fun(A);
  for(int x:A)
    printf("%d | ", x);
}

```

#### Whether C or C++, arrays can be passed only by address 

# Return an Array 

```C
/* int * fun(int n)*/
/*Some compilers don't allow [] replace it with * */
int [] fun(int n){
  int *p;
  p=(int *)malloc(n*sizeof(int));
  return(p);
}

int main(){
  int *A;
  A=fun(3);
}

```

```C++
int [] fun(int n){
  int *p;
  p=(int *)malloc(n*sizeof(int));
  for(int i=0;i<n;i++)
  {
    p[i]=i+1;
  }
  return(p);
}

int main(){
  int *A,sz=7;
  A=fun(sz);
  for(int i=0;i<sz;i++)
  {
    cout<<A[i]<<endl;
  }
}

```

# Structure as a Parameter 
## Call by value Method

```C
struct Rectangle
{
  int len;
  int width;
}
int area (struct Rectangle rect)
{
  rect.len++;
  return rect.len*rect*width;
}

int main(){
  struct Rectangle r={10,20}
  printf("Area=%d",area(r));
}

```

## Call by Reference Method 

```C
struct Rectangle
{
  int len;
  int width;
}
int area (struct Rectangle &rect)
{
  /*The value of Length will be modified*/
  rect.len++;
  return rect.len*rect*width;
}

int main(){
  struct Rectangle r={10,20}
  printf("Area=%d",area(r));
}

```

## Call by Address Method 

```C
struct Rectangle
{
  int len;
  int width;
}
void ChangeLength (struct Rectangle *rect, int v)
{
  /*The value of Length will be modified*/
  rect->len = v;
  return rect.len*rect*width;
}

int main(){
  struct Rectangle r={10,20};
  ChangeLength(&r,20);
  printf("Area Length = %d",r.len);
}

```
#Structures and Functions  

if we want to change the parameter of our structure we need to **Call by reference** and if we need 
to just do a calculation or anyother use we use **Call by value**


#Converting a C program to a C++ Class 

```C
struct Rectangle
{
  int length;
  int width;
}
void initialize(struct Rectangle *r,int l,int w)
{
  r->length=l;
  r->width= w;
}
int area (struct Rectangle r)
{
  return r.length*r.width;
}
void changeLength(struct Rectangle *r,int l)
{
  r->length=l;
}
int main ()
{
  struct Rectangle r;
  initialize(&r,10,5);
  area(r);
  changeLegnth(&r,41);
}

```
### C++ Code 

```C++
class Rectangle
{
    private:
    int length;
    int width;
    public
    void initialize(int l,int w)
    {
      length=l;
      width= w;
    }
    int area ()
    {
      return length*width;
    }
    void changeLength(int l)
    {
      r->length=l;
    }
}
int main ()
{
  Rectangle r;
  r.initialize(10,5);
  r.area();
  r.changeLegnth(41);
}

```

```C++
class Rectangle
{
    private:
    int length;
    int width;
    public
    void Rectangle(int l,int w)
    {
      length=l;
      width= w;
    }
    int area ()
    {
      return length*width;
    }
    void changeLength(int l)
    {
      r->length=l;
    }
}
int main ()
{
  Rectangle r(10,5);
  r.area();
  r.changeLegnth(41);
}

```
# Monolotic Program 

```C++
#include <iostream>
#include<stdio.h>
using namespace std;

int main()
{
    int len=0,wid=0;
    printf("Enter Length and width");
    cin>>len>>wid;
    int area=len*wid;
    int peri= 2*(len+wid);
    cout<<"Area = "<<area<<endl;
    cout<<"Perimeter = "<<peri<<endl;
    return 0;
}

```

# Modular Program 

```C++
#include <iostream>
#include<stdio.h>
using namespace std;


int ComputeArea(int l, int w) {
  return l*w;
}
int ComputePeri(int l, int w) {
  return 2*(l+w);
}
int main()
{
    int len=0,wid=0;
    printf("Enter Length and width");
    cin>>len>>wid;
    cout<<"Area = "<<ComputeArea(len,wid)<<endl;
    cout<<"Perimeter = "<<ComputePeri(len,wid)<<endl;
    return 0;
}

```

# Structure and functions  

```C++
#include <iostream>
#include<stdio.h>
using namespace std;

struct Rectangle {
    int length;
    int width;
};

void initialize(Rectangle *r,int l,int w)
{
  r->length=l;
  r->width=w;
}
int ComputeArea(Rectangle r) {
  return r.length*r.width;
}
int ComputePeri(Rectangle r) {
  return 2*(r.length+r.width);
}
int main()
{
    Rectangle r={0,0};

    int l,w;
    printf("Enter Length and width");
    cin>>l>>w;

    initialize(&r,l,w);

    cout<<"Area = "<<ComputeArea(r)<<endl;
    cout<<"Perimeter = "<<ComputePeri(r)<<endl;

    return 0;
}


```

# Object oriented Program   

in C++ **Structure & Classes** are the **same** but in the **structure everything is by default public**
and in the **Class everything is by default private**

```C++
#include <iostream>
#include<stdio.h>
using namespace std;

class Rectangle {
    private : 
    int length;
    int width;

    public:
    void initialize(int l,int w)
    {
      length=l;
      width=w;
    }
    int ComputeArea() {
      return length*width;
    }
    int ComputePeri() {
      return 2*(length+width);
    }
};
int main()
{
    Rectangle r={0,0};

    int l,w;
    printf("Enter Length and width");
    cin>>l>>w;

    r.initialize(l,w);

    cout<<"Area = "<<r.ComputeArea()<<endl;
    cout<<"Perimeter = "<<r.ComputePeri()<<endl;

    return 0;
}
```

#C++ Class and constructor 

```C++
#include <iostream>
#include<stdio.h>
using namespace std;

class Rectangle
{
    private : 
    int length;
    int width;

    public:

    Rectangle(){ length=width=1;}
    Rectangle(int l,int w);
    int ComputeArea();
    int ComputePeri();
    int getLength(){ return length;};
    void setLength(int l){length=l;};
    ~Rectangle(){cout<<"Destructor";}; 
};
Rectangle::Rectangle(int l,int w)
{
    length=l;
    width=w;
}
int Rectangle::ComputeArea()
{
     return length*width;
}
int Rectangle::ComputePeri()
{
      return 2*(length+width);
}

int main()
{
    Rectangle r(10,10);
    cout<<"Area = "<<r.ComputeArea()<<endl;
    cout<<"Perimeter = "<<r.ComputePeri()<<endl;
    r.setLength(155);
    cout<<"r length = "<<r.getLength()<<endl;
    return 0;
}
```


# Template Class 

```Cpp
class Arithmetic 
{
  private:
    int a;
    int b;
  public:
    Arithmetic(int a,int b);
    int add();
    int sub();
};

Arithmetic::Arithmetic(int a,int b)
{
  this->a = a;
  this->b = b;
}

int Arithmetic::add(int a,int b)
{
  return a+b;
}
int Arithmetic::sub(int a,int b)
{
  return a-b;
}
```

Let's make our code a template

```Cpp

#include <iostream>
#include <stdio.h>
using namespace std;

template<class T>
class Arithmetic 
{
  private:
    T a;
    T b;
  public:
    Arithmetic(T a, T b);
    T add();
    T sub();
};

template<class T>
Arithmetic<T>::Arithmetic(T a, T b)    // because we are using a template class we should add <T>
{
  this->a = a;
  this->b = b;
}

template<class T>
T Arithmetic<T>::add()
{
  return a + b;
}

template<class T>
T Arithmetic<T>::sub()
{
  return a - b;
}

int main()
{
  Arithmetic<int> ar(10, 5);
  cout << "somme = " << ar.add() << endl;
  return 0;
}
```
![image](https://github.com/user-attachments/assets/ab6ad1c4-8487-467f-b9f5-7c6449f36c55)

# Required Setup for Programming 

- online C and Cpp compiler : [**C/C++ Compiler**]( https://www.programiz.com/cpp-programming/online-compiler/)
- C/C++ IDE : [**Codeblocks**](https://www.codeblocks.org/downloads/)
- Dev-C++ : [**mingw**](https://sourceforge.net/projects/orwelldevcpp/files/Compilers/MinGW/)
- Visual Studio Code : [**VSCode**](https://code.visualstudio.com/download)

___ 

# Introduction to DataStructure 


# Stack vs Heap Memory

## Static vs Daynamic Memory Allocation 

```cpp
void main()
{
  int a; // it takes 2 bytes
  int b; // it takes 4 bytes 
}
```
