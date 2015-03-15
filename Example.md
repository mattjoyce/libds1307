
```
#include <Wire.h>
#include <DS1307.h>

int rtc[7];

void setup()
{
  Serial.begin(9600);
/*
  RTC.stop();
  RTC.set(DS1307_SEC,1);
  RTC.set(DS1307_MIN,57);
  RTC.set(DS1307_HR,17);
  RTC.set(DS1307_DOW,4);
  RTC.set(DS1307_DATE,18);
  RTC.set(DS1307_MTH,2);
  RTC.set(DS1307_YR,9);
  RTC.start();
*/
}

void loop()
{
  RTC.get(rtc,true);

  for(int i=0; i<7; i++)
  {
    Serial.print(rtc[i]);
    Serial.print(" ");
  }
  Serial.println();

  delay(1000);

}
```