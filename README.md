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
      * To start off my planning I decided to research the best way to manipulate motors in order to control them how I needed to and I found that the H-Bridge Motor Driver was the best suited to controlling the motors in the way I needed to, it allows me to change speed and direction of the motors with simple lines of code.
    
      * I made the entire circuit in [Tinkercad](https://www.tinkercad.com/things/fkpYd7mgALy-not-beebot-camerons/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard%2Fdesigns%2Fcircuits&sharecode=hNEtSJ4X27Qa3pH9DLSsrnlikMR4CaXaWMVf1GFJPlw) before fiddling with wires in real life. This was so that I could remove any potential for a broken component to break the circuit, seeing as tinkercad is a programmed simulation of what would really happen, there aren't broken components and I can ensure that the reason my circuit might not work is because of how I have wired it and not a broken component.
    
      * Other than circuitry I also have to think about the chassis that the components will sit on, for this, I was thinking of a flat ply-wood plate with little holes to put tabs that I could drill into the hole that is on the hobby motors,
    
      * **Talk about all the 7 functions**
    
      * ![image](https://github.com/user-attachments/assets/c41ade3a-30f2-4565-9ba1-e61625415ecc)
      * ![image](https://github.com/user-attachments/assets/22073cc8-5af2-40f5-afa6-304a6105c8e5)
      * ![image](https://github.com/user-attachments/assets/6852a675-cffc-4f1b-b18f-1a17f53fcc83)
      * ![image](https://github.com/user-attachments/assets/88073326-d4c1-4e19-8b52-755fb7bbe581)
    
   * ### Implementation
      * When writing the code for the NotBeeBot I ran into an issue when trying to implement the pause function, due to the aduino's limitations when I was executing the saved commands in sequence it would wait for all the commands to end before allowing the loop function to run again, this meant that whilst the movement commands were running I couldnt check if any buttons were pressed, and trying to put the checks inside of the movement functions only allowed it to check after each delay in which I would move forward for 750ms so every 750ms it would only check once, the only way to solve this issue would be to use multithreading to allow both the loop function and the movement function to execute simultainously, however this task proved too difficult for me to even begin so I decided to completely wipe the pause function from the project.
   * ### Testing and Evaluation

   * ### Iteration

# References
   * https://projecthub.arduino.cc/Isaac100/getting-started-with-the-hc-sr04-ultrasonic-sensor-7cabe1



