## 第十週 UVA 10226 統計樹名
## 第一步驟
```c
#incldue <stdio.h>
#include <string.h>
char line[1000];
int main()
{
  int T;
  scanf("%d\n\n",&T);
  for(int i=0;i<T;i++)
  {
    int N=0;
    while(gets(line)!=NULL)
    {
      if(strcmp(line,"")==0)
      break;
      printf("%s\n",line);
    }
  }
}
```
## 第二步驟
```c
#incldue <stdio.h>
#include <string.h>
char line[1000];
int main()
{
  int T;
  scanf("%d\n\n",&T);
  for(int i=0;i<T;i++)
  {
    int N=0;
    while(gets(line)!=NULL)
    {
      if(strcmp(line,"")==0)
      break;
      N++;
    }
    printf("tree? %d\n",N);
  }
}
```
## 第三步驟
```c
#incldue <stdio.h>
#include <string.h>
char line[1000];
char tree[10000000][32];
int main()
{
  int T;
  scanf("%d\n\n",&T);
  for(int i=0;i<T;i++)
  {
    int N=0;
    while(gets(line)!=NULL)
    {
      if(strcmp(line,"")==0)
      break;
      N++;
    }
    printf("tree? %d\n",N);
    for(int i=0;i<N;i++)
    {
      printf("%s\n",tree[i]);
    }
  }
}
```
## 第四步驟
```c
#incldue <stdio.h>
#include <string.h>
#include <stdlib.h>
char line[1000];
char tree[10000000][32];
int compare(const void *p1,const void *p2)
{
  return strcmp((char*)p1,(char*)p2);
}
int main()
{
  int T;
  scanf("%d\n\n",&T);
  for(int i=0;i<T;i++)
  {
    int N=0;
    while(gets(line)!=NULL)
    {
      if(strcmp(line,"")==0)
      break;
      strcpy(tree[N],line);
      N++;
    }
    printf("tree? %d\n",N);
    qsort(tree,N,32,compare);
    for(int i=0;i<N;i++)
    {
      printf("%s\n",tree[i]);
    }
  }
}
```
## 第五步驟
```c
#incldue <stdio.h>
#include <string.h>
#include <stdlib.h>
char line[1000];
char tree[10000000][32];
int compare(const void *p1,const void *p2)
{
  return strcmp((char*)p1,(char*)p2);
}
int main()
{
  int T;
  scanf("%d\n\n",&T);
  for(int i=0;i<T;i++)
  {
    int N=0;
    while(gets(line)!=NULL)
    {
      if(strcmp(line,"")==0)
      break;
      strcpy(tree[N],line);
      N++;
    }
    qsort(tree,N,32,compare);
    int ans=1;
    printf("%s",tree[0]);
    for(int i=0;i<N;i++)
    {
      if(strcmp(tree[i],tree[i+1])==0)
      {
        ans++;
      }
      else
      {
        printf("%d\n",ans);
        ans=1;
        printf("%s ",tree[i+1]);
      }
    }
  }
}
```
## 第六步驟
```c
#incldue <stdio.h>
#include <string.h>
#include <stdlib.h>
char line[1000];
char tree[10000000][32];
int compare(const void *p1,const void *p2)
{
  return strcmp((char*)p1,(char*)p2);
}
int main()
{
  int T;
  scanf("%d\n\n",&T);
  for(int i=0;i<T;i++)
  {
    int N=0;
    while(gets(line)!=NULL)
    {
      if(strcmp(line,"")==0)
      break;
      strcpy(tree[N],line);
      N++;
    }
    qsort(tree,N,32,compare);
    if(t>0)printf("\n");
    int ans=1;
    printf("%s",tree[0]);
    for(int i=0;i<N-1;i++)
    {
      if(strcmp(tree[i],tree[i+1])==0)
      {
        ans++;
      }
      else
      {
        printf("%.4f\n",100*ans/(float)N);
        ans=1;
        printf("%s ",tree[i+1]);
      }
    }
    printf("%.4f\n",100*ans/(float)N);
  }
}
```
