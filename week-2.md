# 第二週 指標
# 範例1
```c
#include <stdio.h>
int main()
{
  int n1=10, n2=20, n3=30;
  printf("n1:%d n2:%d n3:%d\n",n1,n2,n3);
  
  int *p = &n1;
  *p = 200;
  printf("n1:%d n2:%d n3:%d\n",n1,n2,n3);
}
```

# 範例2
```c
#include <stdio.h>
int main()
{
  int n1=10, n2=20, n3=30;
  printf("n1:%d n2:%d n3:%d\n",n1,n2,n3);
  
  int *p = &n1;
  *p = 200;
  printf("n1:%d n2:%d n3:%d\n",n1,n2,n3);
  
  int  *p2= &n3;
  *p2 = 300;
  printf("n1:%d n2:%d n3:%d\n",n1,n2,n3);
}
```

# 範例3
```c
#include <stdio.h>
int main()
{
  int n1=10, n2=20, n3=30;
  printf("n1:%d n2:%d n3:%d\n",n1,n2,n3);
  
  int *p = &n1;
  *p = 200;
  printf("n1:%d n2:%d n3:%d\n",n1,n2,n3);
  
  int  *p2= &n3;
  *p2 = 300;
  printf("n1:%d n2:%d n3:%d\n",n1,n2,n3);
  
  p2=p;
  *p2 = 400;
  printf("n1:%d n2:%d n3:%d\n",n1,n2,n3);
}
```
