
# 第七週 字串排序-快速排列
# 字串排列 2.0
```c
#include <stdio.h>
#include <string.h>
char line[100][10];
char temp[10];

int compare(const void * p1,const void * p2)
{
  char * s1 = (char*) p1;
  char * s2 = (char*) p2;
  return strcmp(s1,s2);
}
int main()
{
	int n;
	scanf("%d",&n);
	for(int i=0;i<n;i++)
	{
		scanf("%s",line[i]);
	}
	
  qsort(line,n,10,compare);
  
	for(int i=0;i<n;i++)
	{
		printf("%s\n",line[i]);
	}
}
```
