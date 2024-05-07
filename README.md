#include <ESP8266WiFi.h>
#include <TridentTD_LineNotify.h>

 int Relay = D1;

 #define LINE_TOKEN "Jqf4S29FU5Jbjshw4egcRHbClbXRJjtaNmQ8cjvhY8f"
 char ssid[] = "ABMaker"; 
 char pass[] = "tv357911itv";     

void setup()
{
  Serial.begin(9600);
  pinMode(Relay,INPUT_PULLUP); 

  WiFi.begin(ssid, pass);
  LINE.setToken(LINE_TOKEN);
}

void loop()
{
 int RelayState = digitalRead(Relay);

 if(RelayState == LOW){
  LINE.notify("ตอนนี้ไฟดับ");
  delay(3000);
  while(digitalRead(Relay)== 0){
    
  }
  delay(3000);
  LINE.notify("ตอนนี้ไฟมาเเล้ว");
 }
 else
{

 }
}
