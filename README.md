<a name="Table-of-Contents"></a>
# Table of Contents
   * ## [Development Process](#Development-Process-1)
        * [Planning](#Planning)
        * [Implementation](#Implementation)
        * [Testing](#Testing)
        * [Testing](#Conclusion)
   * ## [Circuit/Wiring Diagrams](#Circuit/Wiring-Diagrams-1)
   * ## [References](#References-1)

<a name="Development-Process"></a>
# Development Process
   * ### Planning
      * <a href="url"><img src="https://github.com/user-attachments/assets/c41ade3a-30f2-4565-9ba1-e61625415ecc" align="right" height=40% width=50% ></a> To start off my planning I decided to research the best way to manipulate motors in order to control them how I needed to and I found that the H-Bridge Motor Driver was the best suited to controlling the motors in the way I needed to, it allows me to change speed and direction of the motors with simple lines of code.
    
      * I made the entire circuit in [Tinkercad](https://www.tinkercad.com/things/fkpYd7mgALy-not-beebot-camerons/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard%2Fdesigns%2Fcircuits&sharecode=hNEtSJ4X27Qa3pH9DLSsrnlikMR4CaXaWMVf1GFJPlw) before fiddling with wires in real life. This was so that I could remove any potential for a broken component to break the circuit, seeing as tinkercad is a programmed simulation of what would really happen, there aren't broken components and I can ensure that the reason my circuit might not work is because of how I have wired it and not a broken component.
    
      * Other than circuitry I also have to think about the chassis that the components will sit on, for this, I was thinking of a flat ply-wood plate with little holes to put tabs that I could screw into the hole on the side of the hobby motors, this design would be very similar to the premade one given to us but instead the sizing would be larger allowing for me to fit more components on top with ease.
    
      * I plan to have 7 buttons, FORWARD, BACKWARDS, LEFT, RIGHT, CLEAR, PAUSE, GO, each movement command will get saved into an array with a max of about 30 commands, then when GO is pressed it will run each command in sequence performing each action after the other with a little wait in between actions, there will also be a beep when a button is pressed and 3 beeps for when the GO button is pressed if it has movement commands to execute, the CLEAR button will clear all saved movement commands from the array, and finally the PAUSE button will halt the NotBeeBot and wait till GO is pressed again to continue the rest of the sequence.
    
      * Looking at both the rubber wheel and the marble ball as what I can use to hold my NotBeeBot up I decided that the marble ball would be the best option, my reasoning is that the rubber ball can pivot which way it's rolling on the fly and has little to no friction, whereas the rubber wheel has to take time to pivot which way its rolling and depending on the direction that it's facing it could cause a lot of friction and actually change how much the NotBeeBot rotates causing the path the bot takes to be way off.
    
      * For the outter shell that is supposed to be appealing to primary school students I think I will laser cut some more plywood in a square with the finger joints and then I can use them to wrap arround the wiring, and then I can cut 8mm diameter circles for the 7 buttons and two holes in the front for the Ultrasonic Distance Sensor, and I will paint the cube to be like a [Minecraft grass block](https://www.google.com/url?sa=i&url=https%3A%2F%2Fminecraft.fandom.com%2Fwiki%2FGrass_Block&psig=AOvVaw09sH0tPHv7PWQKaI33GyIn&ust=1731651961614000&source=images&cd=vfe&opi=89978449&ved=0CBEQjRxqFwoTCOi7prGY24kDFQAAAAAdAAAAABAE) which is a common game for kids to play and will atract their attention keeping them engaged and suiting the age this project is designed for.
    
      * Component List:
         | Name | Quantity | Component |
         | :---:       |  :----:     |     :----:    |
         | U2 | 1 | H-Bridge Motor Driver |
         | M1 & M2 | 2 | Hobby Gearmotor |
         | U3 | 1 | Arduino Uno R3 |
         | Bat1 | 1 | 4 Batteries, AA, yes 1.5V Battery |
         | PIEZO1 | 1 | Piezo |
         | S8 & S9 & S10 & S11 & S12 & S14  | 6 | Pushbutton |
         | DIST1 | 1 | Ultrasonic Distance Sensor (4-pin) |
      

   * ### Implementation
      * When writing the [Code](NotBeeBotCode.txt) for the NotBeeBot I ran into an issue when trying to implement the pause function, due to the Arduino's limitations when I was executing the saved commands in sequence it would wait for all the commands to end before allowing the loop function to run again, this meant that whilst the movement commands were running I couldn't check if any buttons were pressed, and trying to put the checks inside of the movement functions only allowed it to check after each delay in which I would move forward for 800ms so every 800ms it would only check once, the only way to solve this issue would be to use multithreading to allow both the loop function and the movement function to execute simultaneously, however, this task proved too difficult for me to even begin so I decided to completely wipe the pause function from the project.
      <a href="url"><img src="https://github.com/user-attachments/assets/75451d28-659a-4420-b319-9cd94a9e8947" align="right" height=20% width=30% ></a>
      * After setting up all the wiring the same as the [Tinkercad](https://www.tinkercad.com/things/fkpYd7mgALy-not-beebot-camerons/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard%2Fdesigns%2Fcircuits&sharecode=hNEtSJ4X27Qa3pH9DLSsrnlikMR4CaXaWMVf1GFJPlw) version I had to mount it to a chassis, with this I worked with Kyan Erdeljack to help me with the design on [Fusion360](https://www.autodesk.com/au/products/fusion-360/overview?panel=buy&term=1-YEAR&tab=subscription&mktvar002=afc_au_nmpi_ppc&gclsrc=aw.ds&ds_rl=1232386&gad_source=1&affname=17945_&PID=17945&CID=&cfclick=c9bb1341d6bf4355a8cd8fcdd8b67f06) resulting in the [Final Version](bee-bot-template-v3.dxf) laser cut on a plywood piece, the trade-off was that I helped him with his code. This version allowed me to mount all the components comfortably with wiggle room on top of the chassis as well as access the on and off switch for the battery pack. This design was also very reliable and easy to use, mounting the motors was as simple as using little plastic T-pieces and putting a screw through the motor to connect it to the chassis.
    
      * After setting up all the components the main issue I had was accessing the buttons to input commands, to fix this I used new [Pushbuttons](https://core-electronics.com.au/spst-black-push-off-mini-pushbutton-switch-47957.html) that allowed me to wire them away from the breadboard allowing me to add a control panel later on, at this current time I have [this](https://drive.google.com/file/d/1PZJ4p8Wys7UYKFC18_vLBE45zORheZQY/view?usp=sharing) which is also the image on the right, there is no cover due to my lack of knowledge on laser cutting resulting in the design being not exactly suitable for kids which is unfortunate and definetely a fault on my part in terms of time management aswell.


  <a name="Testing"></a>
   * ### Testing, Evaluation and Iteration
      * Here is a [Video](https://drive.google.com/file/d/1NErJ5e0zdEoMrJxAojWGWbAEdsFXxoad/view?usp=sharing) showing the controls getting stored inside a variable and only executing the commands after the GO button is pressed, it also showcases the reverse capability and the CLEAR function all working in sequence.
        
      * When testing my robot I found that a lot of the testing I was going to do would be adjusting the timing for the motors to run allowing for that 15cm measurement and as close to 90-degree turns as I can possibly achieve, however, this came with an issue to do with battery life, as I used the robot more and more the battery drained resulting in varying results over time.
        
      * Despite battery issues I did manage to get a new [Video](https://drive.google.com/file/d/1PXSoWEhVbEcgQeFNJhaXFlGjpG9dIE24/view?usp=sharing) showcasing the NotBeeBot with wheels and an Ultrasonic Distance Sensor all working as intended and also showcasing that the NotBeeBot stops executing commands when faced with an object within 15cm of the Sensor. I did add a couple cardboard cutouts, one for the control panel and one for the Ultrasonic Distance Sensor to sit on the front, I also drew a little smiley face on the front to make it more suitable to kids bringing my NotBeeBot close to the NotBeeBot Plus however the cover isn't exactly suitable.

  <a name="Conclusion"></a>
   * ### Conclusion / Reflection
      * In conclusion I think the final result definetely could have been more suitable for use, due to the lack of the cover the project doesn't feel complete and also is less reliable as tampering with the wiring would be very easy. The NotBeeBot Plus specifies that the project should be appealing the primary school students and whilst the project would be appealing it is for all the wrong reasons, kids would want to play with the wires and eat them for example, this is not safe and wouldnt be suitable to teach kids how to learn sequences.
    
      * Despite the cover, the functionality of the project is highly advanced cohering to the specifications of the NotBeeBot plus perfectly, the code is also well designed making use of features to increase reliability in the circuitry, an example of this is using "INPUT_PULLUP" instead of regular "INPUT" when declaring a pin, this removes the need for a resistor in the physical circuit due to the code looking for a higher current before declaring that the pin is either "1" or "0", this means that the trickle of ground that comes through due to lack of resistance is ignored in the code.
    
      * The code also uses "Else if" statements to remove unnecesary checks and uses an Arduino specific feature of "Switch" and "Case" essentially removing the need for an if statement for each key in an element, and lowering the ammount of writing required for the coder, it is also more efficient for the hardware to read.
    
      * Overall the project meets the NotBeeBot Plus standard and can be used reliably to navigate on a carpet environment, the project is also intuitive and requires no tutorial for usage, simply switch the battery pack on and input the commands.

<a name="Circuit/Wiring-Diagrams"></a>
# Circuit/Wiring Diagrams
   <a href="url"><img src="https://github.com/user-attachments/assets/6852a675-cffc-4f1b-b18f-1a17f53fcc83" align="right" height="240" width="427" ></a>
   <a href="url"><img src="https://github.com/user-attachments/assets/88073326-d4c1-4e19-8b52-755fb7bbe581" align="Center" height="240" width="427" ></a>

   * Here is the Circuit diagram and the Wiring diagram as asked for in the assignment document. You can view them in [Tinkercad](https://www.tinkercad.com/things/fkpYd7mgALy-not-beebot-camerons/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard%2Fdesigns%2Fcircuits&sharecode=hNEtSJ4X27Qa3pH9DLSsrnlikMR4CaXaWMVf1GFJPlw) as well.

# References
   * codebender_ccMore. “How to Use the L293D Motor Driver - Arduino Tutorial.” [Instructables](www.instructables.com/How-to-use-the-L293D-Motor-Driver-Arduino-Tutorial/). Used in the Tinkercad project
   * “Getting Started with the HC-SR04 Ultrasonic Sensor.” [Projecthub.arduino.cc](projecthub.arduino.cc/Isaac100/getting-started-with-the-hc-sr04-ultrasonic-sensor-7cabe1).

   * ### All Links in Documentation:
   * [Code](NotBeeBotCode.txt)
   * [Tinkercad](https://www.tinkercad.com/things/fkpYd7mgALy-not-beebot-camerons/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard%2Fdesigns%2Fcircuits&sharecode=hNEtSJ4X27Qa3pH9DLSsrnlikMR4CaXaWMVf1GFJPlw)
   * [Video](https://drive.google.com/file/d/1NErJ5e0zdEoMrJxAojWGWbAEdsFXxoad/view?usp=sharing)
   * [Image](https://drive.google.com/file/d/1PZJ4p8Wys7UYKFC18_vLBE45zORheZQY/view?usp=sharing)
   * [Main-Video](https://drive.google.com/file/d/1PXSoWEhVbEcgQeFNJhaXFlGjpG9dIE24/view?usp=sharing)

   * [Minecraft grass block](https://www.google.com/url?sa=i&url=https%3A%2F%2Fminecraft.fandom.com%2Fwiki%2FGrass_Block&psig=AOvVaw09sH0tPHv7PWQKaI33GyIn&ust=1731651961614000&source=images&cd=vfe&opi=89978449&ved=0CBEQjRxqFwoTCOi7prGY24kDFQAAAAAdAAAAABAE)
   * [Fusion360](https://www.autodesk.com/au/products/fusion-360/overview?panel=buy&term=1-YEAR&tab=subscription&mktvar002=afc_au_nmpi_ppc&gclsrc=aw.ds&ds_rl=1232386&gad_source=1&affname=17945_&PID=17945&CID=&cfclick=c9bb1341d6bf4355a8cd8fcdd8b67f06)



