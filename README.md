# Portfolio_development
```cpp
#include<HC-SR04.h>
byte x_pin = A0, y_pin = A1, IN1 = 2, IN2 = 3, IN3 = 4, IN4 = 5, trig_pin = 6, echo_pin = 7;
int distances*;
int x,y;
void setup()
{
    pinMode(IN1, OUTPUT);
    pinMode(IN2, OUTPUT);
    pinMode(IN3, OUTPUT);
    pinMode(IN4, OUTPUT);
    HC-SR04.begin(trig_pin, echo_pin);
}
void loop()
{
    distances = distanceInCenti();
    x = analogRead(x_pin);
    y = analogRead(y_pin);

    if(distance[0] < 30)
    {
        digitalWrite(IN1, HIGH);
        digitalWrite(IN2, HIGH);
        digitalWrite(IN3, HIGH);
        digitalWrite(IN4, HIGH);  
    }
    else if(x > 900)
    {
        digitalWrite(IN1, LOW);
        digitalWrite(IN2, HIGH);
        digitalWrite(IN3, LOW);
        digitalWrite(IN4, HIGH);    
    }
    else if(x < 150)
    {
        digitalWrite(IN1, HIGH);
        digitalWrite(IN2, LOW);
        digitalWrite(IN3, HIGH);
        digitalWrite(IN4, LOW);    
    }
    else if(y > 900)
    {
        digitalWrite(IN1, LOW);
        digitalWrite(IN2, HIGH);
        digitalWrite(IN3, HIGH);
        digitalWrite(IN4, LOW);    
    }
    else if(y < 150)
    {
        digitalWrite(IN1, LOW);
        digitalWrite(IN2, HIGH);
        digitalWrite(IN3, LOW);
        digitalWrite(IN4, HIGH);    
    }
    else
    {
        digitalWrite(IN1, HIGH);
        digitalWrite(IN2, HIGH);
        digitalWrite(IN3, HIGH);
        digitalWrite(IN4, HIGH);     
    }
    delay(100);
}
