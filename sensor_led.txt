#include <Servo.h>

long duration;
long distance;
#define trigPin 13
#define echoPin 12

void setup() {
  Serial.begin(9600);
  pinMode(echoPin,INPUT);
  pinMode(trigPin,OUTPUT);
  pinMode(11,OUTPUT);

}

void loop() {
  digitalWrite(trigPin,LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin,HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin,LOW);
  duration = pulseIn(echoPin,HIGH);
  Serial.print(duration);
  Serial.print("\n");
  distance = (duration/2) / 29.1;
  Serial.print(distance);
  Serial.print("\n");
  if (distance < 4 && distance >0) {  // This is where the LED On/Off happens
    digitalWrite(11,HIGH);
    delay(1000);

  }
  else
  {
    digitalWrite(11,LOW);
  }




  }
