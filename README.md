# Automatic-wire-cutter-and-stripper-project
#Code


#include <Stepper.h> 

int numberofstep = 48*64; 
                                  

Stepper motor(numberofstep,9,11,10,6);    // we use pins 9, 11, 10, 6        
void setup() 
{ 
 
  motor.setSpeed(9); // we set motor speed at 9
}
void loop() 
{ 
  motor.step(600); // the motor will run during 600 step (you can change the step)
  motor.step(-800); // the motor will run during 800 step in reverse (you can change the step)

}

#include <LiquidCrystal.h>

// initialize the library by associating any needed LCD interface pin
// with the arduino pin number it is connected to
const int rs = 12, en = 11, d4 = 5, d5 = 4, d6 = 3, d7 = 2;
LiquidCrystal lcd(rs, en, d4, d5, d6, d7);

void setup() {
  // set up the LCD's number of columns and rows:
  lcd.begin(16, 2);
  // Print a message to the LCD.
  lcd.print("Automatic cuuter and stripper");
}

void loop() {
  // set the cursor to column 0, line 1
  // (note: line 1 is the second row, since counting begins with 0):
  lcd.setCursor(0, 1);
  // print the number of seconds since reset:
  lcd.print(millis() / 1000);
}

#include<Servo.h>
Servo Myservo;
int pos;
void setup()
{
Myservo.attach(3);
}

void loop()
{
  
  
for(pos=0;pos<=180;pos++){
Myservo.write(pos);
delay(15);
}
  delay(1000);
  
  for(pos=180;pos>=0;pos--){
Myservo.write(pos);
delay(15);
}
  delay(1000);
  
}
