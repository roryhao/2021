# 第三週 指標、函式
#範例1 
```c
#include <stdio.h>
int a[5]={0,10,20,30,40};
void printall()
{
  for(int i=0;i<5;i++)
  {
    printf("%d ",a[i]);
  }
  printf("\n");
}
int main()
{
          printall();
  int *p = &a[2];
  *p = 222
   printall();
   printf("p心理小紙條記的值是:%d\n",p);
  p = p+2;
  *p = 666;
          printall();
   printf("p心理小紙條記的值是:%d\n",p);
   p--;
   *p = 555;
          printall();
   printf("p心理小紙條記的值是:%d\n",p);
}
```
