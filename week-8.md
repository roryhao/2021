## 第八週
## 第一題 計算國名的次數
```c
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
char a[2000][80];
char b[80];
int compare(const void *p1,const void *p2)
{
  return strcmp((char*)p1,(char*)p2);
}
int main()
{
  int n;
  scanf("%d",&n);
  for(int i=0;i<n;i++)
  {
    scanf("%s",&a[i]);
    gets(b);
  }
  qsort(a,n,80,compare);
  int ans=1;
  printf("%s",a[0]);
  for(int i=0;i<n-1;i++)
  {
    if(strcmp(a[i],a[i+1])!=0)
    {
      printf("%d\n",ans);
      printf("%s",a[i+1]);
      ans=1;
    }
    else ans++;
  }
  printf("%d\n",ans);
}
```


