# iOt-project
Posture detector system code (arduino)
 int flexs = A0; // flex sensor is connected with pin A0 of the Arduino
int flexdata = 0;
int buzzer = 5; // a buzzer is connected with pin 5 of Arduino which is the pwm pin.
 void setup()
{ 
Serial.begin(9600);
pinMode(flexs, INPUT);
pinMode(buzzer, OUTPUT);
}
void loop()
{
flexdata = analogRead(flexs);
Serial.print("flex value;");
Serial.print(flexdata);
Serial.println("");
if( flexdata < 220)
{
 analogWrite(buzzer, 150); 
}
if( flexdata > 220)
{
 analogWrite(buzzer, 0); 
}
 
 delay(1000);
 
}
