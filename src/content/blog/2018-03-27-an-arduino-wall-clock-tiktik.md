---
title: "Arduino Wall Clock: Tiktik"
image: /images/posts/tiktik/setting-rtc-ds3231.png
publishedAt: '2018-03-27'
isFeatured: true
category: 'hardware'
---
I've always had a fondness for [old-fashioned wall clocks like this one that chime every hour](/images/posts/tiktik/antique-wall-clock.jpg). They help me keep track of time throughout the day. So, I began to wonder, Is it possible to create a digital clock that replicates this charming feature? Well, I went ahead and did it! In this blog post, I'm going to explain how it works.

## Equipments

* Arduino UNO R3 Clone
* Servo Motor (PowerHD HD-1800A)
* Real Time Clock (DS3231)
* Hotel Bell

## Flow

1. Real Time Clock component is going to have time. We should upload the time into it. It can time more accurate than clock of Arduino thanks to it's crystals. Also, RTC has an additional battery. The system keeps the time even the electricity cut.
2. Servo engine is going to hit the bell.
3. Arduino is going to be a bridge between servo and rtc. It is going to read rtc time value in each time. If the time is the top of the hour, It is going to triggers servo engine. Then, It will gong.

## Code

### Setting Watch

We should connect the RTC to the Arduino as seen below. Then, set the clock by pushing the code.

![Setting RTC DS3231](/images/posts/tiktik/setting-rtc-ds3231.png)

```c
#include <DS3231.h>

DS3231 rtc(SDA, SCL);

void setup(){
  rtc.begin();

  rtc.setDOW(WEDNESDAY);
  rtc.setTime(15, 0, 0);     // 15:00:00 (24hr format)
  rtc.setDate(27, 3, 2018);   // Set the date to March 27, 2018
}
```

### Last Touch

![A complete project](/images/posts/tiktik/tiktik.png)

```c
// CONFIGURATIONS
const int digital_pin_of_servo = 9;
const int servo_idle_state_degree = 90;
const int servo_active_state_degree = 70;

#include <DS3231.h>
#include <Servo.h>

// initialize the real time clock object.
DS3231 rtc(SDA, SCL);

// initialize the servo
Servo servo;

void setup() {
    rtc.begin();

    servo.attach(digital_pin_of_servo);
}

void loop(){
    String time_string = rtc.getTimeStr(); // "HH:MM:SS"

    String hour_string = time_string.substring(0, 2);  // "HH"
    String minute_string = time_string.substring(3, 5); // "MM"
    String second_string = time_string.substring(6, 8);  // "SS"

    long hour_int = hour_string.toInt(); // 0-23
    long minute_int = minute_string.toInt(); // 0-59
    long second_int = second_string.toInt(); // 0-59

    if (second_int == 0 && minute_int == 0){
    	// time to bang! HH:00:00

        if (hour_int == 0){
            // bang 12 times at the midnight, not 0 time.
           hour_int = 12;         
        }
        else if (hour_int > 12){
            // bang 3 times when the time is 3pm, not 15 times.
            hour_int = hour_int - 12;
        }

        // bang number of hour times.
        for (int i = 0; i < hour_int; i++){
            servo.write(servo_idle_state_degree);              
            delay(1100);

            servo.write(servo_active_state_degree);              
            delay(150);  
        }
      }

  // set the servo to idle degree again.  
  servo.write(servo_idle_state_degree);

  // Wait one second before repeating
  delay (1000);
}
```

## Demo

<iframe width="560" height="315" src="https://www.youtube.com/embed/W1TGt8Ub5BA?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
