# AutomaticHandSanitizer
Source code for the Automatic Hand Sanitizer project.

int trigPin = 9;
int echoPin = 10;
int led = 12;
int led1 = 13;
int motor = 7;
int motorled = 8;
int ir = 5;
void setup()
{
  pinMode(motor,OUTPUT);
  pinMode(motorled,OUTPUT);
  pinMode(ir,INPUT);
   pinMode(led, OUTPUT);
   pinMode(led1, OUTPUT);
   pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  Serial.begin(9600);
}
void loop()
{
 long duration, distance;
  digitalWrite(trigPin,HIGH);
  delayMicroseconds(1000);
  digitalWrite(trigPin, LOW);
  duration=pulseIn(echoPin, HIGH);
  distance =(duration/2)/29.1;
  Serial.print(distance);
  delay(10);
 if((distance<=10)) 
  {
    digitalWrite(led, LOW);
}
   else if(distance>10)
 {
     digitalWrite(led, HIGH);
   }
   if((distance<=4)) 
  {
    digitalWrite(led1, HIGH);
}
   else if(distance>4)
 {
     digitalWrite(led1, LOW);
   }
   if (digitalRead(5)==HIGH)
  {
    digitalWrite(7,LOW);
    digitalWrite(8,HIGH);
    delay(400);
    digitalWrite(7,HIGH);
    digitalWrite(8,LOW);
    delay(3000);
  }
  else
  {                                                                                                                                                                                                                                                                                                                                                    
    digitalWrite(7,HIGH);
    digitalWrite(8,LOW);
    delay(10);                        
  }
}
