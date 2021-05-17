## 第12週
## 一顆星 UVA10062 告訴我頻率 Step01, Step02, Step03
```c
#include <stdio.h>
char line[2000];
int main()
{
  for(int t=0;gets(line);t++)
  {
    int ans[256]={};
    for(int i=0;line[i]!=0;i++)
    {
      char c=line[i];
      ans=[c]++;
    }
   if(t>0)printf("\n");
    for(int i=0;i<256;i++)
    {
      if(ans[i]>0)printf("%d %d\n",i,ans[i]);
    }
  }
}
```
## 利用2層for迴圈, 進行排序的交換
```c
#include <stdio.h>
char line[2000];
int main()
{
  for(int t=0;gets(line);t++)
  {
    int ans[256]={};
    char  c[256]={};
    for(int i=0;i<256;i++)c[i]=i;
    for(int i=0;line[i]!=0;i++)
    {
      char c=line[i];
      ans=[c]++;
    }
    for(int i=0;i<256;i++)
    {
      for(int j=i+1;j<256;j++)
      {
        if(ans[i]>ans[j])
        {
          int temp=ans[i];
          ans[i]=ans[j];
          ans[j]=temp;
          char t=c[i];
          c[i]=c[j];
          c[j]=t;
        }
      }
    }
   if(t>0)printf("\n");
    for(int i=0;i<256;i++)
    {
      if(ans[i]>0)printf("%d %d\n",i,ans[i]);
    }
  }
}
```
## 把第2個比較規則完成
```c
#include <stdio.h>
char line[2000];
int main()
{
  for(int t=0;gets(line);t++)
  {
    int ans[256]={};
    char  c[256]={};
    for(int i=0;i<256;i++)c[i]=i;
    for(int i=0;line[i]!=0;i++)
    {
      char c=line[i];
      ans=[c]++;
    }
    for(int i=0;i<256;i++)
    {
      for(int j=i+1;j<256;j++)
      {
        if(ans[i]>ans[j])
        {
          int temp=ans[i];
          ans[i]=ans[j];
          ans[j]=temp;
          char t=c[i];
          c[i]=c[j];
          c[j]=t;
        }
        if(ans[i]==ans[j]&&c[i]<c[j])
        {
        int temp=ans[i];
          ans[i]=ans[j];
          ans[j]=temp;
          char t=c[i];
          c[i]=c[j];
          c[j]=t;
        }
      }
    }
   if(t>0)printf("\n");
    for(int i=0;i<256;i++)
    {
      if(ans[i]>0)printf("%d %d\n",i,ans[i]);
    }
  }
}
```
## UVA299 交換火車, 先解決 Input, Output
```c
#include <stdio.h>
int a[100];
int main()
{
  int T;
  scanf("%d",&T);
  for(int t=0;i<N;i++)
  {
    scanf("%d",&a[i]);
    for(int i=0;i<N;i++)
    {
      scanf("%d",&a[i]);
    }
    int ans=0;
   printf("Optimal train swapping %d swaps.\n",ans);
  }
}
```
## 利用泡泡排序法, 全部完成
```c
#include <stdio.h>
int a[100];
int main()
{
  int T;
  scanf("%d",&T);
  for(int t=0;i<N;i++)
  {
    scanf("%d",&a[i]);
    for(int i=0;i<N;i++)
    {
      scanf("%d",&a[i]);
    }
    int ans=0;
    for(int k=0;k<N-1;k++)
    {
      for(int i=0;i<N-1;i++)
      {
          if(a[i]>a[i+1])
          {
            int temp=a[i];
            a[i]=a[i+1];
            a[i+1]=temp;
            ans++;
          }
        }
     }
   printf("Optimal train swapping %d swaps.\n",ans);
  }
}
```
##  UVA11321 排排排序, Part 1 先解決 Input, Output
```c
#incldue <stdio.h>
int a[10000];
int main()
{
  int n,m;
  while(scanf("%d%d",&n,&m)==2)
  {
    for(int i=0;i<n;i++)
    {
      scanf("%d",a[i]);
    }
    printf("%d %d\n",n,m);
    for(int i=0;i<n;i++)
    {
      printf("%d\n",a[i]);
    }
  }
}
```
## 之後步驟 發明函式幫交換
```c
#incldue <stdio.h>
int a[10000];
void swag(int i,int j)
{
  int temp=a[i];
  a[i]=a[j];
  a[j]=temp;
}
int main()
{
  int n,m;
  while(scanf("%d%d",&n,&m)==2)
  {
    for(int i=0;i<n;i++)
    {
      scanf("%d",a[i]);
    }
    for(int i=0;i<n;i++)
    {
      for(int j=i+1;j<n;j++)
      {
        if(a[i]%m>a[j]%m)swag(i,j)
        if(a[i]%m==a[j]%m)
        {
          if(a[i]%2==0 && a[j]%2!=0)swag(i,j);
          if(a[i]%2!=0 && a[j]%2!=0 && a[i]<a[j])swag(i,j);
          if(a[i]%2==0 && a[j]%2==0 && a[i]>a[j])swag(i,j);
        }
      }
    }
    printf("%d %d\n",n,m);
    for(int i=0;i<n;i++)
    {
      printf("%d\n",a[i]);
    }
  }
}
```
