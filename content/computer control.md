Title: 電腦控制
Date: 2017-07-11 20:32
Category: Arduino
Tags: notes, Arduino
Slug: Arduino-computer control
Author: 40423222

參考Arduino快速紹手指南(Maik Schmidt)

<!-- PELICAN_END_SUMMARY -->
<hr>

### 需要材料:
<a href="https://40423222.github.io/2017springcd_hw/blog/Arduino-LED.html">LED</a>: 一個
<br> 
<a href="http://coopermaa2nd.blogspot.tw/2011/05/arduino.html">Arduino Uno</a>: 一個

<hr>

### 電路圖(Circuit diagram):
<img src="./../data/computer control/Circuit diagram.png" width="480">

<hr>

### 程式碼(Code):
<pre class="brush: python">
//使用方式: 開啟序列輸入1或2來啟動LED
const unsigned int ledPin = 13; //const代表這變數不會改變

void setup() {
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  if(Serial.available() > 0) { //回傳資料
    int command = Serial.read(); //讀取資料
    if(command == '1') { //鍵盤要輸入的值為1,注意變數以外的值,要使用''包住
      digitalWrite(ledPin, HIGH);
      Serial.print("輸入1號:"); //標題名稱
      //注意要將Serial.print("輸入1號:");放置於Serial.println("LED ON");上一行,避免出錯
      Serial.println("LED ON"); //顯示LED ON,注意要使用""
    }
    else if(command == '2') {
      digitalWrite(ledPin, LOW);
      Serial.print("輸入2號:");
      Serial.println("LED OFF");
    }
    else{
      Serial.print("Unknown command:"); //標題名稱,下方可選擇要顯示的值
      Serial.println(command); //顯示ASCII碼(十進位)
      //Serial.println(command, DEC); //顯示ASCII碼(十進位)
      //Serial.println(command, HEX); //顯示ASCII碼(十六進位)
      //Serial.println(command, OCT);
      //Serial.println(command, BIN); //顯示ASCII碼(二進位),
      //注意:程式會自動將第一位數給消去(總共有8位數),因為第一位數一定是零
      //Serial.println(command, BYTE); //已不被支援
    }
  }
}
/*
可輸入鍵盤上所有的符號,但只會一個個讀取.
例如:輸入15,系統會先讀取1後再讀取5
ASCII資續:https://zh.wikipedia.org/wiki/ASCII
決定數字系統
int decimal = 4711;
int binary = B1001001100111;
int octal = 011147;
int hexadecimal = 0x1267;
二進位用B來開頭,八進位用0來開頭,十六進位用0x
*/
</pre>