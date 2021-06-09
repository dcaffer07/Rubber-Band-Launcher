# Rubber-Band-Launcher
This is the official repository of the servo controlled rubber band launcher!

### Table of Contents 
##### [Overview and Planning](https://github.com/dcaffer07/Rubber-Band-Launcher/blob/main/README.md#overview-1) 
##### [Criteria & Contraints](https://github.com/dcaffer07/Rubber-Band-Launcher/blob/main/README.md#criteria-and-constraints)
##### [Materials](https://github.com/dcaffer07/Rubber-Band-Launcher/blob/main/README.md#materials-1)
##### [Cad Design on OnShape](https://github.com/dcaffer07/Rubber-Band-Launcher/blob/main/README.md#cad-deesign-on-onshape)
##### [Code from Aurduino.cc](https://github.com/dcaffer07/Rubber-Band-Launcher/blob/main/README.md#code-from-aurduinocc-1) 
##### [Fabrication, Lazer cutting and assembly](https://github.com/dcaffer07/Rubber-Band-Launcher/blob/main/README.md#fabrication-lazer-cutting-and-assembly-1)
##### [Reflection](https://github.com/dcaffer07/Rubber-Band-Launcher/blob/main/README.md#reflection-1)

### Quik Links Toooooooo...
##### [Onshape Design](https://cvilleschools.onshape.com/documents/0dd79b927bf5381224f5dd72/w/ed12cf5fd3aabc61b859f110/e/7e691b198bd380ac2878944e)
##### [Code on Aurduino]()
##### [Wireing Design on Tinker Cad]()
##### [Pseudo Code](https://docs.google.com/document/d/15zp4eDbrOS1N2ccocQCLKSBN3L3EhV48NTX2vnqM8p8/edit)
##### [Design Blueprint on Google Drawings](https://docs.google.com/drawings/d/1qZ76DlaDXZF_Cr9F3ZvZoBRgsG1Z4dknvrHgPDDP1vY/edit?usp=sharing)

### Overview
##### What are you trying to accomplish?
>We (Jabari and Dominick), plan to design a device that shoots a rbber band. This will be accomplished by a rubber band being pulled tightly around variouse different 3D printed objects along with a servo at the end that will cause the rubber band to fly when the servo turns.  The tention of the rubber band will allow for this to occur and function. We will use variouse differnt platforms such as OnShape, Tinkercad, and Aurduino, to help us plan ot the variouse steps pof the process ad reach our end goal.   
##### What’s it going to do?
>As stated, the goal of the project id to use the variouse platforms we have learned to use to LAUNCH A RUBBER BAND!
##### What’s it going to look like?
>The base will be a peice of acrilic that is almost like a table with 4 3D printed legs hlding it up.  The aurduino, breadboard, and batteries will be attacthed to the side of the base facing the floor, and the buttons, servo, and other parts to stretch the rubber band will be located on the top part of the table. 
##### Who is incharge of what?
>Dominick: He will be in charge of helping create an initial design, and than will be in charge of designing and creating it on OnShape.  Additionally, Dominick will be there during the lazer cutting and 3D printing process, and will put together the design and all of its parts.  
>Jabari: He will also be helping research design ideas to get the procces going.  Additionally, Jabari will be in charge of creating the code, and wiring for the design.  He will impliment his wiring design in the lab and int the final project.

### Criteria and Constraints
##### The servo had to be (Criteria)
> - Able to fit in a hand
> - Battery-powered
> - One Button turns the servo one way
> - The other button turns the servo the other way
##### Constraints
> - The servo could only be made of materials found in the CHS sigma lab
> - This was out first time doing many of these things such as lazer cutting, preparing for 3D printing, and being in the lab!
> - Partners could not colaborate as easily as we were in different spaces and areas throughout.

### Materials
##### For structure
> - 1 arduino sheild
> - 1 prototyping sheild
> - 1 mini breadboard
> - SG92R 180 micro servo -micro servo horn double armed
> - 2 panal mount pushbuttons
> - 1 Battery mount
> - 7 socket button head cap screws - #4-40 x 0.375
> - 4 25x.5 aluminum hex male female standoff
> - 3 1-72 Machine screw nuts
> - 8 4-40 Michne screw nuts
> - 1 9v battery
> - 2 M2 machine screws and M2 machine nuts
> - RUBBER BAND - soft strecth type 3
> - Acrylic platform - 100cm x 200cm x 3cm
> - 3D printed material
##### For Wiring
> - 

### Cad Design on OnShape 
> When creating this design, it was important that the structure was functional and easy to use without it being over complicated.  Additionally, it was important that the structure fit the criteria of being able to fit in one hand, which sounds simple, however this become a very large and difficult factor when the rubber band needs to be stretched to a point of being able to shoot with some umph.  This is when we cam up with the idea of wraping the rubber band, in lther words, we constructed this design in simolaritie to how one owould shoot a ruber band with their hand (hook the band arond your middel finger, wrap it around your thumb which is pointed up, and than hook it to your pointer finger pointing to where you want the band to shoot, and then release it by straigtening your middle finger).  This is the design that we decided to go with, only instead of a pointer finger there was a 3D printed triangle, and instead of a thum there was another 3D printed trinagle, and finally, instead of a middle finger, there is a servo which releases the rubber band by turning its head.  
##### Steps
> 1) Create a base with all of the nessesary space and holes for additional attatchments including legs.
> 2) Create the triangels which stretch the rubber band and allow for it to fly and attcth thos strategically to the base.
> 3) Add all buttons, servos, ardunios, and battery mounts to the base which already contain muach of the holes for these things.
##### Create a final assembly!
> At this point all that needs to be done is to put everything together into a final assembly...
![image](https://user-images.githubusercontent.com/71406831/121391595-899d8080-c91c-11eb-9da7-e67129a070b4.png)
> We are ready to print ad lazer cut! 
[Link to full OnShape design](https://cvilleschools.onshape.com/documents/0dd79b927bf5381224f5dd72/w/ed12cf5fd3aabc61b859f110/e/7e691b198bd380ac2878944e)

### Code from Aurduino.cc
c++
#include <Servo.h>

Servo myServo;

int btn1pin = 2;
int btn2pin = 3; 
int servoPin = 9;
int btn1State;
int btn2State;
  
void setup() {
 Serial.begin(9600); 
 myServo.attach(servoPin);
 
 pinMode(btn1pin,INPUT);
  pinMode(btn2pin,INPUT);
}
void loop() {
  btn1State = digitalRead(btn1pin);
 btn2State = digitalRead(btn2pin);
 
 Serial.print("button 1: ");
 Serial.print(btn1State);
 Serial.print("\t button 2: ");
 Serial.println(btn2State);
 if(btn1State == HIGH)
 { 
 
 myServo.write(180); 
 
 }
 
if(btn2State == HIGH)
 { 
 
 myServo.write(90); 
 
 } 

}c++

### Fabrication, Lazer cutting and assembly
##### The beggining
> To be honest, the begginig was both very easy and complicated.  The easy part was waiting for or designs to 3D print and lazer cut, however the not so fun part was getting to that point, as it was our first time having to do this and it was pretty complicated gettig it inly the folder just right.  However once we figured that out with the help of peers and Mr. H we were off to the races.
##### The part after the beggining
> At this point our parts have been 3D printed, and so it was time to get the base right.  This was a pretty interesting process, as we simple put our design into a folder, and than watched as the Lazer Cutter made out the holes and cuts that needed to be preformed.  At this point, we now have the base and have gathered all of the meterials such as the battery, aurduino, mini breadbard, nuts and screws, and so it is time to assemble.
##### The point when we start to assemble
> At this point it was time to assemble and all went very smoothly except for one problem which was that I kept putting the legs on the wrong side of the base, whoch made everything not work and complicated.  After this problem was resolved, we had some problems with the trinagle where the holes were not quite big enough, and so this was solved by simply taking a screw driver and making the holes just a little bit bigger, the same had to be done with the battery mount.  From there it was smooth sailing, as there were no problems, and all that was left was wiring everything up.
##### Wiring
> This process was also reletively easy, the only part that was a bit difficult was getting the wires attatched to the buttons, howver this problem was quikly resolves with the help of Mr. H and peers.  From here we used the design that we had createed in [tinker cad]() to help us implement the neccesary parts in real life.  
##### Final Product!!!!!!!!!!!!!!!!!!!!!!
> This was the moment we had been waiting for and after several weeks of hard work it was time to test it. When we did we were excited to see everything work but the servo would freak out after pressing the button as the current had no where to go and no where to stop.  We resolved this pronlem by putting a resister in. With this, the buttons and everything worked, however the rubberbands that we had acces to were to big, but this was an easy fix as we simpply eeded smaller rubber bands and all things fnctioned great.  SUCCESS!
##### Here are some images of final product
![This is the finished product](https://github.com/dcaffer07/Rubber-Band-Launcher/blob/main/engineering%20pic2.jpg?raw=true)![This is the finished product](https://github.com/dcaffer07/Rubber-Band-Launcher/blob/main/engineering%20pic.jpg?raw=true)

### Reflection
