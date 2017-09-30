Title: Blink 啟動LED
Date: 2017-09-30 13:23
Category: Arduino
Tags: Arduino
Slug: LED
Author: 40423222

以下為Arduino Uno板的LED燈實驗

<!-- PELICAN_END_SUMMARY -->

### 需要材料:
<a href="https://40423222.github.io/2017springcd_hw/blog/Arduino-LED.html">LED</a>: 一個<br/>
<a href="http://coopermaa2nd.blogspot.tw/2011/05/arduino.html">Arduino Uno</a>: 一個

### 電路圖(Circuit diagram)

<img src="./../data/Blink/Circuit diagram.png" width="480" />

### 程式碼(Code)

<pre class="brush: python">
void setup() {
  pinMode(13,OUTPUT);
  //13腳位為輸出
}

void loop() {
  digitalWrite(13,HIGH);
  //13腳位輸出HIGH
  delay(1000);
  //持續1秒
  digitalWrite(13,LOW);
  //13腳位輸出LOW
  delay(1000);
}
</pre>

### 參考網站:
Lad1 Blink:
<a href="http://coopermaa2nd.blogspot.tw/2010/12/arduino-lab1-blinking-led.html">http://coopermaa2nd.blogspot.tw/2010/12/arduino-lab1-blinking-led.html</a><br/>
參考對象:
<img src="./../data/參考對象/Cooper Maa.png" width="150" />