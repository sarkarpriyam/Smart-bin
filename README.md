# Smart Bin using Arduino UNO

THIS IS A QUICK AND EASY BUILD, AND DOESN'T REQUIRE MANY THINGS.

IN THIS PROJECT WE CAN VERY EASILY AUTOMATE A DUSTBIN, WHICH OPENS WHENEVER WE BRING OUR HAND IN-FRONT OF THE ULTRASOUND SENSOR.

## Components Required

* Arduino
* IR sensor
* Servo motor

## Circuit Diagram

![circuit](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi4Mv5i5tcHlLERdBe7fNxNpsVfWvbBCMOaeB-VAEp54r8oSdVFGmrtnIJtKYZJJhwjonrzuseM9MfGaFXzYMMIqYQd5931L07sqDuWOnPOdWBiXJwD9Z-XBIYyR1X5USUWjWiHYHFFQvnmMQ_9ZV_KA09voJKft4_LQHXI-mAN_WAIucWRP3uHa6oP/s1600/circuit%20%281%29.png)

## Program for Arduino

```cpp
#include <Servo.h>


const int analogInPin = A0;
int sensorValue = 0;               
int servoPin = 9;
int i = 0;

Servo servo;

void setup() {
 
servo.attach(servoPin);
}

void loop() {
 
  sensorValue = analogRead(analogInPin);           
 
  if(sensorValue < 600){
    for (int i = 0; i<=180; i++){
    servo.write(120);
    delay(10);
   }
  }
  servo.write(i); 
                     
}
```