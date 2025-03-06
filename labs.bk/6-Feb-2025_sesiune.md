---
title: sesiune
date: 6-Feb-2025
description: 
tags: []
---

```c

#include <stdio.h>

int ex5(void) {
    int arri[]={1,2,3};//3x4
    int *pi=arri;
    char arrc[]={1,2,3};
    char *pc=arrc;

    // aici pt valorile unde este 8 raspunsul pt exament este 4 deoarece a specificat el
    // ca pointerii vor fi pe 4 bytes
    // iar specificatorul de format este %lu deoarece cu %d nu ar fi mers
    printf("%lu\n",sizeof(arri));//12
    printf("%lu\n",sizeof(pi));//8
    printf("%lu\n",sizeof(arrc));//3
    printf("%lu\n",sizeof(pc));//8



    printf("Hello, World!\n");
    return 0;
}

//incomplet
void ex3(){
    int v[]={1,2,3,6};
    int suma=0;
    float media;
    int k=0;
    int *pv=v;
    for(int i=0;i<4;i++){
        suma += *(pv+i);
        k++;
    }
    media=suma/k;
    printf("%d\n",suma);
    printf("%f\n",media);

}


void ex6(){
    float arr[5]={1.5,10.0,23.4,80.45,3.5};
    float *ptr1=arr;
    float *ptr2=ptr1 + 3;
    printf("val 1 = %f\n",*ptr2);
    printf("val 2 = %d\n",ptr2-ptr1);

}


int isPrim(int x){
    int i,ok=1;
    if(x==1)
        return 0;

    for (i = 2; i <= x / 2 && ok; i++)
    {
        if(x%i==0){
            ok = 0;
        }
    }
    if(ok){
        return 1;
    }
    return 0;
}


void ex4(){
    int a, b,i;
    scanf("%d", &a);
    scanf("%d", &b);
    for (i = a; i <= b;i++){
        if(isPrim(i)){
            printf("%d ", i);
        }
    }
}

int main(){
    ex3();
    return 0;
}
```
