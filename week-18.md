## 視訊
## step01_安裝Processing-Sketch-Library-AddLibrary,找video,安裝它, 便能在程式 import processing.video.星; 再宣告視訊變數 Capture cam 再用size(640,480)開個傳統的視窗要放視訊,最後用 println( Capture.list() ); 印出所有的視訊鏡頭
```c
import processing.video.*;  //開vedio外掛
//安裝新的函式庫Processing Video Library後，沒有紅色底線
Capture cam;  //global全域變數:全球全部的變數VS.某函式的變數
//視訊鏡頭
void setup(){
  size(640,480);  //20年前的電腦
  println(Capture.list());
}//會印出你電腦的全部視訊鏡頭，ex. 筆電、HD、WebCam
```

## step02_接著step01,補上幾行。cam = New Capture(this, 視訊名字); cam.start(); 在void setup()裡 if( cam.available() )  cam.read() 讀視訊, 再用 set(0,0,cam)畫到畫面
```c
import processing.video.*; 
Capture cam;
void setup(){
  size(640,480); 
  println(Capture.list());
  cam=new Capture(this,"HD WebCam");  //初始畫面
  cam.start();  //開啟視訊鏡頭
}void draw(){
  if(cam.available())cam.read();  //讀視訊出來
  set(0,0,cam);
}
```

## step03_老師在Teams裡有video.mov的影片檔可下載,請下載後,拉到新的Processing視窗,寫新的程式,改用 Movie move 來取代step02的 Capture cam, 大部分和step02很像,只差在new Movie(this,檔名) 還有 movie.play() 或 movie.loop()
```c
import processing.video.*; 
Movie movie;
void setup(){
  size(640,480); 
  movie=new Movie(this,"video.mov");
  movie.play(); //movie.loop(); //play重做一次 loop持續重作
}void draw(){
  if(movie.available()){  //如果影片有空，就會讀出視訊
     movie.read(); 
  }
  set(0,0,movie);
}
```
