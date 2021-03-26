# 第五週 陣列與指標
##難題
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
