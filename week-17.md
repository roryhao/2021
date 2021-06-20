## 打字練習工具
## step01_利用String line宣告一個字串變數,變數可以變動,所以在程式很重要, 再用text()畫出字
```c
void setup(){
  size(400,200);
  textSize(40);
}
String line="world";
void draw(){
  background(0);
  text("hello",100,100);  //固定字串
  text("line" ,100,150);  //變數
}
```

## step01-2利用字串的+可以把2個字串接起來變比較長的字串,同時在mousePressed()裡,line=line+新的字母,也能變長
```c
void setup(){
  size(400,200);
  textSize(40);
}
String line="";
String Q   ="hello";
void draw(){
  background(0);
  text("Q:   "+Q   ,100,100);  //左邊有個字串，所以又邊有個字串hello
  text("You:"+line ,100,150);  //左邊有個字串，所以又邊有個字串
}
void mousePressed(){
  line=line+"a";  //原本line什麼都沒有，滑鼠按了之後+a
}
```

## step02-1延序前一步驟,但把mousePressed()改成keyPressed(), 同時 line = line + key; 讓按的字母可以變長
```c
void setup(){
  size(400,200);
  textSize(40);
}
String line="";
String Q   ="hello";
void draw(){
  background(0);
  text("Q:"+Q    ,100,100);  //左邊有個字串，所以又邊有個字串hello
  text("A:"+line ,100,150);  //左邊有個字串，所以又邊有個字串
}
void keyPressed(){
  line=line+key;  //原本line什麼都沒有，鍵盤輸入甚麼就顯示什麼
}
```

## step02-2_如果key==BACKSPACE時,就要用 line = line.substring(0, len-1)來讓字串變短一點點,而 int len=line.length()會得到字串的原本長度, 還有要判斷小寫字母、大寫字母
```c
void setup(){
  size(400,200);
  textSize(40);
}
String line="";
String Q   ="hello";
void draw(){
  background(0);
  text("Q:"+Q    ,100,100);  //左邊有個字串，所以又邊有個字串hello
  text("A:"+line ,100,150);  //左邊有個字串，所以又邊有個字串
}
void keyPressed(){
  int len=line.length();  //新函式
  if(key>='a' && key<='z')line = line +key; //小寫
  if(key>='A' && key<='Z')line = line +key; //大寫
  if(key == BACKSPACE)line=line.substring(0,len-1); //用倒退鑑不會出現空格
}
```

## step02-3_老師解釋substring(開始,結束)的意思,很像for(int i=0;i小於26;i++)會做26次的右邊界不包含, 而且會有當機的問題,用len大於0來保護len不要變負的
```c
void setup(){
  size(400,200);
  textSize(40);
}
String line="";
String Q   ="hello";
void draw(){
  background(0);
  int len=len.length();
  text(len,100,50);
  text("Q:"+Q    ,100,100);  //左邊有個字串，所以又邊有個字串hello
  text("A:"+line ,100,150);  //左邊有個字串，所以又邊有個字串
}
void keyPressed(){
  int len=line.length();  //新函式
  if(key>='a' && key<='z')line = line +key; //小寫
  if(key>='A' && key<='Z')line = line +key; //大寫
  if(key == BACKSPACE && len>0)line=line.substring(0,len-1); //避免字串-1
  //用倒退鑑不會出現空格(右邊檢左邊等於多少字母，就會印出多少字母)
}
```

## step03-1_為了要算分數,我們在 keyPressed()裡,加入 if(key==ENTER) 去算分數。算分數要用字串比對 line.equals(Q)==true 成立時,score++, 否則 score-- 再印出分數
```c
void setup(){
  size(400,200);
  textSize(40);
}
String line="";
String Q   ="hello";
void draw(){
  background(0);
  text("Q:"+Q    ,100,100);  //左邊有個字串，所以又邊有個字串hello
  text("A:"+line ,100,150);  //左邊有個字串，所以又邊有個字串
}
void keyPressed(){
  int len=line.length();  //新函式
  if(key>='a' && key<='z')line = line +key; //小寫
  if(key>='A' && key<='Z')line = line +key; //大寫
  if(key == BACKSPACE)line=line.substring(0,len-1); //用倒退鑑不會出現空格
}
```

## step02-3_老師解釋substring(開始,結束)的意思,很像for(int i=0;i小於26;i++)會做26次的右邊界不包含, 而且會有當機的問題,用len大於0來保護len不要變負的
```c
void setup(){
  size(400,200);
  textSize(40);
}
String line="";
String Q   ="hello";
void draw(){
  background(0);
  text("Score:"+score,100,50);
  text("Q:"+Q    ,100,100);  //左邊有個字串，所以又邊有個字串hello
  text("A:"+line ,100,150);  //左邊有個字串，所以又邊有個字串
}
int score=0;
void keyPressed(){
  int len=line.length();  //新函式
  if(key>='a' && key<='z')line = line +key; //小寫
  if(key>='A' && key<='Z')line = line +key; //大寫
  if(key == BACKSPACE && len>0)line=line.substring(0,len-1); //避免字串-1
  //用倒退鑑不會出現空格(右邊檢左邊等於多少字母，就會印出多少字母)
  if(key == ENTER){
    if(line.equals(Q)==true){ //如果equals(Q)正確，分數+1，否則-1
      score++;
    }
    else score--;
  }
}
```

## step03-2_利用陣列,來讓題目變更多。 String [] Q = {好多字串} 再配 int Qi=0 來挑選 Q[Qi] 的字來考試, 答對時 Qi++ 並加分, 小心,Qi太大會當掉哦
```c
void setup(){
  size(400,200);
  textSize(40);
}
String line="";
String []Q  ={"hello","world",other};
int Qi=0; //第幾個Q Q[Qi] Q[0] Q[1] Q[2]...
void draw(){
  background(0);
  text("Score:"+score,100,50);
  text("Q:"+Q[Qi],100,100);  //左邊有個字串，所以又邊有個字串hello
  text("A:"+line ,100,150);  //左邊有個字串，所以又邊有個字串
}
int score=0;
void keyPressed(){
  int len=line.length();  //新函式
  if(key>='a' && key<='z')line = line +key; //小寫
  if(key>='A' && key<='Z')line = line +key; //大寫
  if(key == BACKSPACE && len>0)line=line.substring(0,len-1); //避免字串-1
  //用倒退鑑不會出現空格(右邊檢左邊等於多少字母，就會印出多少字母)
  if(key == ENTER){
    if(line.equals(Q[Qi])==true){ //如果equals(Q)正確，分數+1，否則-1
      score++;
      Qi++; //換下一筆Q[0]變Q[1]...
      line="";
    } //算分數
    else score--;
  }
}
```
