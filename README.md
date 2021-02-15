# Rubber-Band-Launcher
This is the official repository of the servo controlled rubber band launcher!

## Rubber Band Launcher Pre-Planning
#####
What are you trying to accomplish?
We are planning to have a servo turn a tightened rubberband, with the goal that when you press a button, the servo that is holding the band will release the band, and it will fly.  When the band has been released, there will be a different button that causes the servo to turn back into its original position so that another band can be tightened and released again.

Criteria (goals):
What’s it going to do?
Launch a rubber band

What’s it going to look like?
There will be almost a table that is small enough to be hand held, and the battery and wiring will be hooked to the side facing the ground and than on the top there will be the buttons, servo, and other material that is used to tighten the rubber band into the launch position.
Any optional goals, should things go well?  (added lights, buzzers, etc)
We could possibly make the platform shooter move using a servo.

Whose researching what?
Dominick: will research other servo rubber band launchers for ideas.  
Jabari: will research design ideas.

## Link to OnShape Doc w/ Design
##### https://cvilleschools.onshape.com/documents/0dd79b927bf5381224f5dd72/w/ed12cf5fd3aabc61b859f110/e/853e3d7f52100516492cad3c

## Psuedo Code
c++

Program start
Identify my servo

Initialize agngles to 180 from 180

Define variables and pins
 x to left
 x to right

Void setup
  Serial Begin
  Pinmode left
      Pin x to left
  Pinmode right
      Pin x to right
Servo angle 180 from 180 

Void Loop
  Digital Read
  Serial Print angel, left, depending
  Serial Print degree, 180
  
Void Loop
  Digital Read
  Serial Print angel, right depending
  Serial Print degree, 180
c++     
      
