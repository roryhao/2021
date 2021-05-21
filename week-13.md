## 第十三週 倒數計時器
## 事前練習1 先將Processing開啟,使用size()還有background()開出有背景色的視窗
```c
size (1024,400);//視窗的大小
background(220,50,55);//視窗的顏色
```

## 事前練習2 互做mousePressed的互動,先有void setup()及 void draw(),再用if(mousePressed) 及else來切換
```c
void setup()
{
  size (1024,400);
}
void draw()
{
  if(mousePressed)background(220,50,55);//如果按視窗才會顯示這個顏色
  else background(20,150,80);//否則都是這個顏色
}
```

## 事前練習3 用textSize()調字大小,text()畫出字,void mousePressed()做按下去的動作
```c
void setup()
{
  size (1024,400);
}
void draw()
{
  if(mousePressed)background(220,50,55);//如果按視窗才會顯示這個顏色
  else background(20,150,80);//否則都是這個顏色
  textSize(50);//字型大小
  text(a,100,100);
}
int a=0;
void mousePressed(){//按一次，視窗上的數字加一
  a++;
}
```

## 第一步驟 利用hour()小時,minute()分鐘,second()秒,再用特別的字串加法,顯示垷在的時間
```c
void setup()
{
  size(1024,400);
}
void draw()
{
  background(20,150,80);
  textSize(50);
  int h=hour();
  int m=minute();
  int s=second();
  text("Now:" +h +":" +m +":" +s,100,100);//輸出現在時間是幾時幾分幾秒
}
```

## 第二步驟 利用 textFont()改成字型createFont()的標楷體, 甪乘上60 60 來算出總秒數
```c
void setup()
{
  size(1024,400);
  textFont(createFont("標楷體",50));//輸出的國字為標楷體且大小50
}
void draw()
{
  background(20,150,80);
  textSize(50);
  int h=hour();
  int m=minute();
  int s=second();
  fill(250,50,0);//字的顏色
  text("Now:" +h +":" +m +":" +s,100,100);//輸出現在時間是幾時幾分幾秒
  int total=h*60*60+m*60+s;//總秒數
  text("總秒數"+total,100,200);//輸出總秒數
}
```

## 第三步驟 把總秒數 像找零錢方法 利用 取餘數 算出時、分、秒
```c
void setup()
{
  size(1024,400);
  textFont(createFont("標楷體",50));//輸出的國字為標楷體且大小50
}
void draw()
{
  background(20,150,80);
  textSize(50);
  int h=hour();
  int m=minute();
  int s=second();
  fill(250,50,0);//字的顏色
  text("Now:" +h +":" +m +":" +s,100,100);//輸出現在時間是幾時幾分幾秒
  int total =h*60*60 +m*60+s;//現在時間的總秒數
  int total2=12*60*60+0*60+0;//目標時間的總秒數
  text("總秒數"+total,100,200);//輸出總秒數
  int ans=total2-total;//目標時間-現在時間
  int H=ans/60/60%60,M=ans/60%60,S=ans%60; //將秒數分別變成小時、分鐘
  text("還剩下: " +H +":" +M +":" +S,100,300);//剩餘多少時間
}
```
