#include<LiquidCrystal.h>
LiquidCrystal lcd(12, 11, 5, 4, 3, 2);

const int pbpin = 8;
const int ledpin = 10;

void setup()
{
  pinMode(pbpin, INPUT);
  pinMode(ledpin, OUTPUT);
  pinMode(A0, INPUT);
  Serial.begin(9600);
  lcd.begin(16,2);
}

void loop()
{
  int state = digitalRead(pbpin);
  
  if(state == HIGH)
  {
    digitalWrite(10, HIGH);
    
    int reading = analogRead(A0);
  	float voltage = reading * (5000.0 / 1024.0);
  	float temp = (voltage - 500) / 10;
  	float Ktemp = temp + 273.15;
    
    Serial.print(temp);
  	Serial.print(" *C");
  	Serial.print("\n");
    Serial.print("temperature in Kelvin: ");
    Serial.print(Ktemp);
    Serial.print(" K");
    Serial.print("\n");
    
    lcd.setCursor(0,0);
    lcd.print(temp);
    lcd.print(" *C");
    
    lcd.setCursor(0,1);
    lcd.print(Ktemp);
    lcd.print(" K");
    delay(2000);
    
    while(1)
    {
      lcd.clear();
      break;
    }
  }
  else
  {
    digitalWrite(10, LOW);
  }
}
