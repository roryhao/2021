# 第五週 字串排序
# 又是一個絕望的一天(難題)
# 步驟1
```c
#include <stdio.h>
int main()
{
    char line[10]="decline";
    char line2[10]={'p','r','o','p','e','r','\0'};

    printf("%s\n",line);
    printf("%s\n",line2);
}
```

# 步驟2
```c
#include <stdio.h>
int main()
{
    char line[10]="decline";
    char line2[10]={'p','r','o','p','e','r','\0'};

    printf("%s\n",line);
    printf("%s\n",line2);


    char line3[]="majority";
    printf("%s\n",line3);
    char line4[]={'m','a','j','o','i','t','y'};
    printf("%s\n",line4);
}
```

# 步驟3
```c
int main()
{
    ///五個字串，每個字串10格
    char line[5][10]={"decline","proper","majority","bullet","shop"};
    for(int i=0;i<5;i++)
    {
        printf("%s\n",line[i]);
    }
}
```

# 步驟4
```c
#include <stdio.h>
#include <string.h>
/// strcmp() strcopy ()
int main()
{
    char line[10]="majority";
    char line2[10]="ask";
    if(strcmp(line,line2)>0)
    {
        printf("左邊大\n");
    }
    else
    {
        printf("右邊大\n");
    }
}
```

# 完整版
```c
#include <stdio.h>
#include <string.h>
char line[100][10];
int main()
{
	int n;
	scanf("%d",&n);
	for(int i=0;i<n;i++)
	{
		scanf("%s",&line[i]);
	}
	char temp[10];///用來交換的temp字串
	for(int i=0;i<n;i++)
	{
		for(int j=i+1;j<n;j++)
		{
			if(strcmp(line[i],line[j])>0)///大小錯
			{
				strcpy(temp,line[i]);	///temp=a;
				strcpy(line[i],line[j]);///a=b;
				strcpy(line[j],temp);	///b=temp;
			}///就交換
		}
	}
	for(int i=0;i<n;i++)
	{
		printf("%s\n",line[i]);
	}
}
```
