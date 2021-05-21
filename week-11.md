## 第十一週
## 1.示範課本的 qsort() 及 compare()函式
```c
#include <stdio.h>
#include <stdlib.h>
int a[10]={4,8,3,7,5,2,9,1,6,10}
int compare(const void *p1,const void *p2)
{
  int d1=*(int *)p1;
  int d2=*(int *)p2;
  if(d1>d2) return 1;
  if(d1==d2)return 0;
  if(d1<d2) return -1;
}
int main()
{
  qsort(a,10,sizeof(int),compare)
  for(int i=0;i<10;i++)
  {
    printf("%d",a[i]);
  }
}
```
## 2.複習 struct 結構
```c
#include <stdio.h>
struct data{
  int ans;
  char c;
}
int main()
{
  box.ans=1;
  box.c='A';
  printf("%c %d\n",box.c,box.ans);
}
```

## 3.UVA 10062 告訴我頻率。先示範 step01 讀資料, step02 印資料
```c
#include <stdio.h>
char line[2000];
int main()
{
  for(int t=0;gets(line);t++)
  {
    if(t>0)printf("\n");
    printf("blahblahblah\b");
    printf("blahblahblah\b");
    printf("blahblahblah\b");
  }
}
```

## 4.step03 用 ans[ ] 來存答案, step04字串的迴圈來統計, step05印出來
```c
#include <stdio.h>
char line[2000];
int ans[256];
int main()
{
  for(int t=0;gets(line);t++)
  {
    for(int i=0;i<256;i++)
    {
      ans[i]=0;
    }
    for(inti=0;line[i]!=0;i++)
    {
      char c=line[i];
      ans[c]++;
    }
    if(t>0)printf("\n");
    for(int i=0;i<256;i++)
    {
      if(ans[i]>0)
      printf("%d %d\n",i,ans[i]);
    }
  }
}
```
