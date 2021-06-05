## 第十五週

## 複習倒數計時,second()秒鐘,textSize()字型大小,test()畫出字,setup()做一次,draw()每秒做60次
```c
void setup()
{
  size(400,200);
  textSize(40);
}
void draw()
{
  background(40,150,200);
  int s=second();
  text(s,100,100);
}
```

## 倒數計時,利用餘數及減法,來做出9到0的倒數計時
```c
void setup()
{
  size(400,200);
  textSize();
}
void draw()
{
  background(40,150,200);
  int s=second();
  text(9-s%10,100,100);
}
```

## Sound播出聲音,要先用Sketch-Library-Add Library加入Sound外掛程式,接下來照著老師hackmd的教學,剪貼程式碼,再把mp3檔放進去PDE寫程式的地方
```c
import processing. sound. *;
SoundFile player;
void setup()
{
  size(400,200);
  player=new SoundFile(this,"tada.mp3"); //把mp3檔放進去PDE寫程式的地方
}
void draw()
{
  background(51,114,191);
}
void mousePressed()
{
  player.play();  //滑鼠一按便開始播放
}
```

## 把第01,02,03合併,以step02為主,插入step03的宣告、初始化、play播放,但每秒播60次,很吵
```c
import processing. sound. *;
SoundFile player;
void setup()
{
  size(400,200);
  player=new SoundFile(this,"tada.mp3"); //把mp3檔放進去PDE寫程式的地方
}
void draw()
{
  background(51,114,191);
  int s=second();
  text(9-s%10==0)player.play(); //0秒時開始播放音訊，但因為if()會進去60次，導致很吵
}
```

## 要有更好的聲音播放,所以if( player.isPlaying() )時,要stop(), 否則 play(), 記得要放bell 換bell mp3哦
```c
import processing. sound. *;
SoundFile player;
void setup()
{
  size(400,200);
  player=new SoundFile(this,"bell.mp3"); //把mp3檔放進去PDE寫程式的地方
}
void draw()
{
  background(51,114,191);
}
void mousePressed()
{
  if(player.isPlaying())
  {
    player.stop();
  }
  else
  {
    player.play();
  }
}
```

## 開新程式,切換成p5 js模式,利用 MaKey教授的網頁,將processing to p5 js converter轉換,貼上,執行,就會開網頁
```c
function setup() //先將第一個倒計時程式利用「processing to p5 js converter網站轉換」，接著執行就會開網頁
{
  creatCancas(400,200);
  textSize(40);
}
function draw()
{
  vackground(41,109,207);
  let s=second();
  text(s,100,100);
}
  
```
