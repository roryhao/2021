# 第三週 結構
# 範例1
```c
#include <stdio.h>
struct POINT
{
    float x,y;
};
int main()
{
    stuct POINT a={4.1,3.2};
    printf("%f %f\n",a.x,a.y);
}
```

# 範例2 (舊式寫法:c.x=b.x; c.y=b.y;)

```c
#include <stdio.h>
struct DATA{
    int x,y;
}a[3];
struct DATA b={100,200};

int main()
{
    struct DATA c;
    c=b;
}
```
# 範例3
```c
#include <stdio.h>
struct POINT
{
    float x,y;
};
int main()
{
    stuct POINT a={4.1,3.2};
    printf("%f %f\n",a.x,a.y);
    
    a.x=1;
    a.y=2;
     printf("%f %f\n",a.x,a.y);
}
```

# 範例4

```c
#include <stdio.h>
struct DATA
{
    int x,y;
}a[3];
struct DATA b={100,200};
int main()
{
    for(int i=0;i<3;i++)
    {
        printf("a[%d]:%d %d\n",i,a[i].x, a[i].y);
    }
    printf("b: %d %d\n",b.x,b.y);
   struct DATA c;
   printf("c: %d %d 像亂碼\n",c.x,c.y);

   c=b;
   printf("c: %d %d\n",c.x,c.y);
}
```

# 範例5(難,結合指標及陣列)
```c
#include <stdio.h>
struct POINT{
    float x,y,z;
};

struct POINT point[5]={{0,0,0},{1,0,0},{0,1,0},{0,0,1},{1,1,1}};

int main()
{
    struct POINT * p = & point[0];
    printf("%.2f %.2f %.2f\n",p->x,p->y,p->z);

    p++;
    printf("%.2f %.2f %.2f\n",p->x,p->y,p->z);

    p++;
    printf("%.2f %.2f %.2f\n",p->x,p->y,p->z);

}

```
