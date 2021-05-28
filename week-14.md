## 第十四週 大樂透抽籤java
## step01在 setup()設定裡, 用亂數random(60)取出小於60的數,用text()印出來,textSize()字大小設大一些
```c
void setup()
{
  size(300,200);  //框框大小
  float ans=random(60); //數字範圍
  textSize(30); //字體大小
  text(ans,0,30) //印出(數字，位置)
}
```

## step02修改後,利用(int)random(60)將float轉成int, 利用mosuePressed()來改亂數,記得background()清背景
```c
void setup()
{
  size(300,200);
  textSize(30);
}
int ans=0;
void draw() //畫圖，每秒60次
{
  background(44,156,240); //背景圖案
  //int ans=(int)random(60) 如果放這裡，會直接亂數且無法停止
  text(ans,30,30);
}
void mousePressed()
{
  ans=(int)random(60);  //滑鼠按下才亂數
}
```

## step03_亂數洗牌,先宣告Java的陣列 int [] a = {...}, 再用for迴圈,印出陣列的值, mousePressed()時,利用random()挑2個數i1,i2,將a[i1],a[i2]交換
```c
int []a={1,2,3,4,5,6,7,8,9,10}; //java的陣列
void setup()
{
  size(300,200);
  textSize(30);
}
int ans=0;
void draw() //畫圖，每秒60次
{
  background(#2C9CFO);
  for(int i=0;i<10;i++)
  {
    text(a[i],i*40,100);  //印出(陣列，位置)
  }
}
void mousePressed()
{
  int i1=(int)ranbom(10);
  int i2=(int)ranbom(10);
  int temp=a[i1];
      a[i1]=a[i2];
      a[i2]=temp;
}
```

## step04_大樂透,使用作弊的方法,事先亂數洗牌10000次,再拿前面6個數字,當成中獎號碼。小心,Java陣列的宣告有點特別, 要記得裡面用for迴圈放值
```c
//大樂透 抽獎時，49顆球中抽6球
int []a={49};
void setup()
{
  size(300,200);
  textSize(30);
  for(int i=0;i<6;i++)
  {
    text(a[i],i*40,100);
  }
}
void mousePressed()
{
  for(int i=0;i<10000;i++)  //作弊大樂透，已經事先選好號碼
  {
  int i1=(int)ranbom(49);
  int i2=(int)ranbom(49);
  int temp=a[i1];
      a[i1]=a[i2];
      a[i2]=temp;
  }
}
```

## step05大樂透的球,會慢慢掉出來,有個bug是會N++超過6顆球
```c
//大樂透 抽獎時，49顆球中抽6球
int []a={49};
void setup()
{
  size(300,200);
  textSize(30);
  for(int i=0;i<10000;i++)
  {
  int i1=(int)ranbom(49);
  int i2=(int)ranbom(49);
  int temp=a[i1];
      a[i1]=a[i2];
      a[i2]=temp;
  }
}
int N=0;
void draw()
{
  background(#2C9CF0);
  for(int i=0;i<N;i++)
  {
    fill(255);
    ellipse(50+i*50,100,40,40); //印出橢圓(位置)
    textAlign(CENTER,CENTER); //印一行數字(位置在中間)
    fill(0);
    text(a[i],50+i*50,100);
   }
}
void mousePressed()
{
  N++;  //每按一次，增加一顆球
}
```

## 使球不會突然出現，而是慢慢地從右邊往左移
```c
int []a={49};
void setup()
{
  size(500,300);
  textSize(30);
  for(int i=0;i<40;i++) a[i]=i+1;   //
  for(int i=0;i<10000;i++)
  {
  int i1=(int)ranbom(49);
  int i2=(int)ranbom(49);
  int temp=a[i1];
      a[i1]=a[i2];
      a[i2]=temp;
  }
}
int N=0,roolling=0;
void draw()
{
  background(#2C9CF0);
  for(int i=0;i<N;i++)
  {
    int x=50+i*50;
    if(i==N-1 && rolling>0)
    {
      x+=rolling;
      rolling-=5;
    }
    fill(255);
    ellipse(x,100,40,40); //印出橢圓(位置)
    textAlign(CENTER,CENTER); //數字對齊(位置在中間)
    fill(0);
    text(a[i],x,100);
   }  //49球，挑6球
}
void mousePressed()
{
  N++;  //其實數字已經決定好了，只是慢慢印出來，讓人以為是慢慢抽
  rolling=500;
}
```
