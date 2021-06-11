## 第十六週 轉輪抽籤
## step01_利用ellipse()畫出圓形,設定圓心,寬,高,再利用void setup()設定size()大小,在draw()有background(RGB三色)
```c
void setup()
{
  size(400,200);
}
void draw()
{
  background(57,255,127);
  ellipse(50,50,80,80); //畫圓(圓心，寬，高);
}
```

## step02_使用arc()來畫圓弧,參數和ellipse很像,圓心,寬,高,後面start,stop利mouseX除50.0 來輔助了解PI 3.14 就是半圓,換了色彩才看得清楚
```c
void setup()
{
  size(400,200);
}
void draw()
{
  background(57,255,127);
  fill(255); //白色
  ellipse(100,50,180,180); //畫圓(圓心，寬，高);
  fill(255,0,0); //紅色
  float stop=mouseX/50.0; //滑鼠的移動座標，往右紅色增加、往左紅色減少
  text(stop,200,100); 
  arc(100,100,180,180,0,stop);  //(圓心，寬，高，圓弧，stop)
}
```

## step03_老師解釋 度degrees 及 弧度radians 的差別, 並且改用 radians()函式,來幫助你理解 start 和 stop 代表開始角度、結束角度
```c
void seyup(){
  size(400,200);
  fill(255,0,0);
  textSize(40);
}
int degree=0;
void draw()
}
  background(57,255,127);
  float stop=radians(degree); //弧度 徑度
  text(degree,200,100); //360度 航海
  text(stop,200,150);
  arc(100,100,180,180,0,stop);
  if(mousePressed)degree++
{
```

## step04_了解arc()裡的start,stop要用radians單位後,我們利用 shift移動量的變數,讓它每秒轉動60度,利用radians()換算角度
```c
void setup(){
  size(400,200);
  fill(255,0,0);
  textSize(40);
}
flaot shift=0;
void draw()
{
  background(57,255,127);
  float start=radians(90+shift);
  float stop=radians(180+shift);
  arc(100,100,180,180,start,stop);
  shift+=1; //轉速
}
```

## step05_利用變數v讓轉動的速度可調整,慢慢 v乘0.99變慢, 最後很慢時停下來
```c
void setup(){
  size(400,200);
  fill(255,0,0);
  textSize(40);
}
flaot shift=0,v=10;
void draw()
{
  background(57,255,127);
  float start=radians(90+shift);
  float stop=radians(180+shift);
  arc(100,100,180,180,start,stop);
  if(b>0.001){ //還有速度時轉動
    shift+=v; //轉速
    v=v*0.99; //速度會慢慢減速
  }
  text(shift,200,100); //印出shift
  text(v,200,150); //印出轉動的速度
}
```

##  step06_利用mousePressed()觸發 random()讓v可以是亂數,每按一次mouse就會有新的轉動速度,也把停止速度改一下。+5是為了讓v介於5-15之間
```c
void setup(){
  size(400,200);
  fill(255,0,0);
  textSize(40);
}
flaot shift=0,v=10;
void mousePressed()
{
   //v=random(10); 0...10.0
  v=random(10)+5; //5...15.0 至少保底5
}
void draw()
{
  background(57,255,127);
  float start=radians(90+shift);
  float stop=radians(180+shift);
  arc(100,100,180,180,start,stop);
  if(b>0.1){ //還有速度時轉動
    shift+=v; //轉速
    v=v*0.99; //速度會慢慢減速
  }
  text(shift,200,100); //印出shift
  text(v,200,150); //印出轉動的速度
}
```

##  step07_利用for迴圈,畫出24片小Pizza,會組合成很大的pizza,分別利用if(餘數)來填上不同的顏色,start及stop的計算看起來很複雜,其實就是把整個圓蓋起來
```c
void setup(){
  size(400,200);
  fill(255,0,0);
  textSize(40);
}
flaot shift=0,v=10;
void mousePressed()
{
   //v=random(10); 0...10.0
  v=random(10)+5; //5...15.0 至少保底5
}
void draw()
{
  background(57,255,127);
  for(int i=0;i<24;i++)
  {
    if(i%3=0)fill(0); //3的倍數，黑色
    if(i%3=1)fill(255); //3的倍數餘1，白色
    if(i%3=2)fill(200,180,0) //3的倍數餘2，橘色
    float start=radians(90+shift);
    float stop=radians(180+shift);
    arc(100,100,180,180,start,stop);
  }
  if(b>0.1){ //還有速度時轉動
    shift+=v; //轉速
    v=v*0.99; //速度會慢慢減速
  }
  text(shift,200,100); //印出shift
  text(v,200,150); //印出轉動的速度
}
```
