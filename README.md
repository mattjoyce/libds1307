# libds1307

DS1307 Real-Time Clock (RTC) library for Arduino

## About

This library provides an interface for the DS1307 Real-Time Clock chip with Arduino. It was one of the early and most popular DS1307 libraries in the Arduino community.

Originally created by Matt Joyce in 2009 and hosted on Google Code at `code.google.com/p/libds1307/`.

## History

- **March 31, 2009** - Initial release announced on the Arduino forums
- **August 2012** - Updated for Arduino IDE v1.0.1 compatibility with contributions from:
  - RIVA (http://arduino.cc/forum/index.php?action=profile;u=112546)
  - rcim (http://arduino.cc/forum/index.php?action=profile;u=134640)
- **2016** - Google Code shut down
- **2025** - Migrated to GitHub for preservation

## Features

- Read/write time and date from DS1307 RTC
- Start/stop clock functionality
- BCD format handling
- Simple API for Arduino projects
- Compatible with Arduino Wire library

## Installation

1. Download this repository
2. Copy the libds1307 folder to your Arduino libraries directory
3. Restart the Arduino IDE
4. Include the library in your sketch: `#include <DS1307.h>`

## Usage

```cpp
#include <Wire.h>
#include <DS1307.h>

int rtc[7];

void setup() {
  Serial.begin(9600);

  // Optional: Set the time
  // RTC.stop();
  // RTC.set(DS1307_SEC, 0);
  // RTC.set(DS1307_MIN, 30);
  // RTC.set(DS1307_HR, 14);
  // RTC.set(DS1307_DOW, 1);      // Day of week
  // RTC.set(DS1307_DATE, 8);
  // RTC.set(DS1307_MTH, 11);
  // RTC.set(DS1307_YR, 25);      // Year (2025)
  // RTC.start();
}

void loop() {
  RTC.get(rtc, true);

  Serial.print(rtc[DS1307_HR]);
  Serial.print(":");
  Serial.print(rtc[DS1307_MIN]);
  Serial.print(":");
  Serial.println(rtc[DS1307_SEC]);

  delay(1000);
}
```

## API Reference

### Constants

- `DS1307_SEC` - Seconds (0-59)
- `DS1307_MIN` - Minutes (0-59)
- `DS1307_HR` - Hours (0-23)
- `DS1307_DOW` - Day of week (1-7)
- `DS1307_DATE` - Date (1-31)
- `DS1307_MTH` - Month (1-12)
- `DS1307_YR` - Year (0-99, representing 2000-2099)

### Methods

- `RTC.get(int *rtc, boolean refresh)` - Get all time/date values into an array
- `RTC.get(int component, boolean refresh)` - Get individual component
- `RTC.set(int component, int value)` - Set individual component
- `RTC.start()` - Start the RTC
- `RTC.stop()` - Stop the RTC

## References

- [Original Arduino Forum Post (2009)](https://forum.arduino.cc/t/library-for-ds1307-real-time-clock/37654?page=4)
- [Kevin Fundarek's Blog Post (2015)](https://kevinfundarek.wordpress.com/2015/03/28/arduino-rtcs-unixtime-and-the-ds1307-h-library/)
- [Google Code Archive](https://code.google.com/archive/p/libds1307/)

## License

This library was released as open source. Please use and modify as needed for your Arduino projects.

## Author

Matt Joyce (2009-2012)

## Preservation

This repository was created in 2025 to preserve this historically significant Arduino library after the shutdown of Google Code. The code remains unchanged from the last Google Code version (August 2012).
