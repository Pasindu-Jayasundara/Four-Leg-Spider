#include <HCSR04.h>
#include <Servo.h>

Servo servo1; // front left 
Servo servo2; //rear left
Servo servo3; // front right
Servo servo4; // rear right

int middle = 90;
int endPoint = 50;//80
int stepDelay = 400;

const int trigPin = 9;  
const int echoPin = 3; 

float duration, distance;  

void setup()
{
  servo1.attach(10); 
  servo2.attach(5);
  servo3.attach(11);
  servo4.attach(6);

  pinMode(trigPin, OUTPUT);  //trig
  pinMode(echoPin, INPUT);   //echo
  Serial.begin(9600);

}

void loop() {

  digitalWrite(trigPin, LOW);  
  delayMicroseconds(2);  
  digitalWrite(trigPin, HIGH);  
  delayMicroseconds(10);  
  digitalWrite(trigPin, LOW);  

  duration = pulseIn(echoPin, HIGH);
  distance = (duration*.0343)/2; 
  delay(100);  

  if(distance > 20){

    servo1.write(middle);
    servo2.write(middle);
    servo3.write(middle);
    servo4.write(middle);
    delay(stepDelay);
  
    servo1.write(middle - endPoint);//left back
    delay(stepDelay);
    servo3.write(middle + endPoint);//right back
    delay(stepDelay);
    servo2.write(middle - endPoint);//front left
    delay(stepDelay);
    servo4.write(middle + endPoint);//front right
    delay(stepDelay);
  
  }else{
    servo1.write(middle);
    servo2.write(middle);
    servo3.write(middle);
    servo4.write(middle);
    delay(stepDelay);
  
    servo3.write(middle + endPoint);//right back
    delay(stepDelay);

    servo4.write(middle + endPoint);//front right
    delay(stepDelay);
  }
  
}
