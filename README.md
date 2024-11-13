<a name="Table-of-Contents"></a>
# Table of Contents
   * ## [Development Process](#Development-Process-1)
        * [Planning](#Planning)
        * [Implementation](#Implementation)
        * [Testing](#Testing)
        * [Evaluation](#Evaluation)
        * [Iteration](#Iteration)
   * ## [Circuit/Wiring Diagrams](#Circuit/Wiring-Diagrams-1)
   * ## [References](#References-1)

<a name="Development-Process"></a>
# Development Process
   * ### Planning
      * <a href="url"><img src="https://github.com/user-attachments/assets/c41ade3a-30f2-4565-9ba1-e61625415ecc" align="right" height=40% width=50% ></a> To start off my planning I decided to research the best way to manipulate motors in order to control them how I needed to and I found that the H-Bridge Motor Driver was the best suited to controlling the motors in the way I needed to, it allows me to change speed and direction of the motors with simple lines of code.
    
      * I made the entire circuit in [Tinkercad](https://www.tinkercad.com/things/fkpYd7mgALy-not-beebot-camerons/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard%2Fdesigns%2Fcircuits&sharecode=hNEtSJ4X27Qa3pH9DLSsrnlikMR4CaXaWMVf1GFJPlw) before fiddling with wires in real life. This was so that I could remove any potential for a broken component to break the circuit, seeing as tinkercad is a programmed simulation of what would really happen, there aren't broken components and I can ensure that the reason my circuit might not work is because of how I have wired it and not a broken component.
    
      * Other than circuitry I also have to think about the chassis that the components will sit on, for this, I was thinking of a flat ply-wood plate with little holes to put tabs that I could drill into the hole that is on the hobby motors,
    
      * I plan to have 7 buttons, FORWARD, BACKWARDS, LEFT, RIGHT, CLEAR, PAUSE, GO, each movement command will get saved into an array with a max of about 30 commands, then when GO is pressed it will run each command in sequence performing each action after the other with a little wait in between actions, there will also be a beep when a button is pressed and 3 beeps for when the GO button is pressed if it has movement commands to execute, the CLEAR button will clear all saved movement commands from the array, and finally the PAUSE button will halt the NotBeeBot and wait till GO is pressed again to continue the rest of the sequence.
    
      * Looking at both the rubber wheel and the marble ball as what I can use to hold my NotBeeBot up I decided that the marble ball would be the best option, my reasoning is that the rubber ball can pivot which way it's rolling on the fly and has little to no friction, whereas the rubber wheel has to take time to pivot which way its rolling and depending on the direction that it's facing it could cause a lot of friction and actually change how much the NotBeeBot rotates causing the path the bot takes to be way off.
    
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
      * When writing the [Code](NotBeeBotCode.txt) for the NotBeeBot I ran into an issue when trying to implement the pause function, due to the Arduino's limitations when I was executing the saved commands in sequence it would wait for all the commands to end before allowing the loop function to run again, this meant that whilst the movement commands were running I couldn't check if any buttons were pressed, and trying to put the checks inside of the movement functions only allowed it to check after each delay in which I would move forward for 750ms so every 750ms it would only check once, the only way to solve this issue would be to use multithreading to allow both the loop function and the movement function to execute simultaneously, however, this task proved too difficult for me to even begin so I decided to completely wipe the pause function from the project.
    
      * 
        
   * ### Testing and Evaluation
      * Here is a [Video](https://drive.google.com/file/d/1NErJ5e0zdEoMrJxAojWGWbAEdsFXxoad/view?usp=sharing) showing the controls getting stored inside 
      * When testing my robot I found that a lot of the testing I was going to do would be adjusting the timing for the motors to run allowing for that 15cm measurement and as close to 90-degree turns as I can possibly achieve, however, this came with an issue to do with battery life, as I used the robot more and more the battery drained 

   * ### Iteration


<a name="Circuit/Wiring-Diagrams"></a>
# Circuit/Wiring Diagrams
   <a href="url"><img src="https://github.com/user-attachments/assets/6852a675-cffc-4f1b-b18f-1a17f53fcc83" align="right" height="240" width="427" ></a>
   <a href="url"><img src="https://github.com/user-attachments/assets/88073326-d4c1-4e19-8b52-755fb7bbe581" align="Center" height="240" width="427" ></a>

   * Here is the Circuit diagram and the Wiring diagram as asked for in the assignment document. You can view them in [Tinkercad](https://www.tinkercad.com/things/fkpYd7mgALy-not-beebot-camerons/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard%2Fdesigns%2Fcircuits&sharecode=hNEtSJ4X27Qa3pH9DLSsrnlikMR4CaXaWMVf1GFJPlw) as well.

# References
   * https://projecthub.arduino.cc/Isaac100/getting-started-with-the-hc-sr04-ultrasonic-sensor-7cabe1

   * ### All Links:
   * [Code](NotBeeBotCode.txt)
   * [Tinkercad](https://www.tinkercad.com/things/fkpYd7mgALy-not-beebot-camerons/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard%2Fdesigns%2Fcircuits&sharecode=hNEtSJ4X27Qa3pH9DLSsrnlikMR4CaXaWMVf1GFJPlw)
   * [Video-1](https://drive.google.com/file/d/1NErJ5e0zdEoMrJxAojWGWbAEdsFXxoad/view?usp=sharing)



