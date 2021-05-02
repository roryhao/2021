## 第八週
## 第一題 UVA 10420 計算國名的次數
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

## 第二題 UVA 10226 統計樹的數目
```c
#include <stdio.h>
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
	for(int t=0;t<T;t++)
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
		printf("%s ",tree[0]);
		for(int i=0;i<N-1;i++)
		{
			if(strcmp(tree[i],tree[i+1])==0)
			{
				ans++;
			}
			else 
			{
				printf("%.4f\n",100*ans/(float)N);
				printf("%s ",tree[i+1]);
				ans=1;
			}
		}
		printf("%.4f\n",100*ans/(float)N);
	}
}
```


