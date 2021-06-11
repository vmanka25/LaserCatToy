# LaserCatToy

* Psuedo code
```C++
// portable button controlled servo
 // This will move a servo back and forth, based on pressing 2 buttons
// startup the servo


void setup() {
    // turn on buttons and servos
}

void loop() {
    // first thing is to read both buttons 
    buttonsState1 = digitalRead(buttonPin1);
    buttonsState2 = digitalRead(buttonPin2);
    // use IF statements to determine if a button is being pressed 
     // IF first button is pressed, go clockwise (use button toggle code)
     // IF second button is pressed, go counter clockwise, (use button toggle code) 
      // it might be cool to make this happen at a random speed 
      // it might be cool to make this happen at a random speed
      //how do we stop the servo?

}
```
* Link to google doc

https://docs.google.com/document/d/1j5MdDleZUu98y5knqwqvsEoK6fcETlX_6FQEk443yGY/edit?usp=sharing




# Tuesday March 7

I am working on the code(Leo)  I need to put more work in on that because I am a little behind.  I learned that i need to manage my time better especially in class.  I will be working on it daily trying to catch up and I will probably need to come to office hours on friday.  

# code

// Ja & Quinns Mouse clicker code.

/*
   Original code was Created by ArduinoGetStarted.com

   This example code is in the public domain

   Tutorial page: https://arduinogetstarted.com/tutorials/arduino-button-servo-motor
*/

#include <Servo.h>

// constants won't change
const int BUTTON_PIN = 7; // Arduino pin connected to button's pin
const int SERVO_PIN  = 9; // Arduino pin connected to servo motor's pin

Servo servo; // create servo object to control a servo

// variables will change:
int angle = 0;          // the current angle of servo motor
int lastButtonState;    // the previous state of button
int currentButtonState; // the current state of button
int state = 0;
int rando = 0;


void setup() {
  Serial.begin(9600);                // initialize serial
  pinMode(BUTTON_PIN, INPUT_PULLUP); // set arduino pin to input pull-up mode
  servo.attach(SERVO_PIN);           // attaches the servo on pin 9 to the servo object

  servo.write(angle);
  currentButtonState = digitalRead(BUTTON_PIN);
}


void loop() {
  lastButtonState    = currentButtonState;      // save the last state
  currentButtonState = digitalRead(BUTTON_PIN); // read new state

  if (lastButtonState == LOW && currentButtonState == HIGH) {
    Serial.println("The button is pressed");

    // This flips state on or off, starting or stopping the servo
    if (state == 0)
      state = 1;
    else if (state == 1)
      state = 0;

    // 
  }


  if (state == 1) {
    rando = random(1, 180);     //Random speed and direction when button pushed
    servo.write(rando);         
    delay(3000);                //Changes every 3 seconds
 
  }
  if (state == 0) {     //Stops when button is pressed second time after 3 second interval
    servo.write(90);
  }
}
#Overview

The goal of this project was to keep a cat entertained by spinning an attached laser around randomly for at least a minute.
the code is above
materials
3d printer,laser cut plastic, arduino components.
The First thing I did while making the toy was design a hollow cone to house the electronics, I then made sure everything fit on Onshape. After I did the cone I designed something to hold the laser on an angle, so that when the motor spun it it would make a circle. after I finished designing the toy on Onshape, we printed the cone and laser cut the base. There were a couple problems assembling the cone. I designed the cone to small so fitting everything was pretty hard, another issue, was the laser made a tiny circle. I think If I were to redesign it I would chose a more efficient shape that used less filament, but had more room for everything. when testing the toy my cats ripped out a wire before I could take a video, so all I got were pictures.
https://cvilleschools.onshape.com/documents/19440993f3284106738a8272/w/7b91d9de4ebb5ec9eb933385/e/f77b28bb06586606944d1c6d
