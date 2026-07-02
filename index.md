
# Assistive Smart Jacket

Sensors send out sound and record the time it takes for the sound waves' echoes to return to the sensors' receptors. The time recorded can be used to find the distance an object is from the sensor in the direction of the emitted sound. When the distance of an object from the sensor passes a certain threshold, buzzers are triggered (faster frequency corresponds with closer distance). 


<!---You should comment out all portions of your portfolio that you have not completed yet, as well as any instructions:--> 
<!--- This is an HTML comment in Markdown -->
<!--- Anything between these symbols will not render on the published site -->


| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Nathan Liu | Lynbrook High School | Bio(medical)engineering | Rising Sophomore

**Replace the BlueStamp logo below with an image of yourself and your completed project. Follow the guide [here](https://tomcam.github.io/least-github-pages/adding-images-github-pages-site.html) if you need help.**

![Headstone Image](logo.svg)
  
# Final Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/F7M7imOVGug" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your final milestone, explain the outcome of your project. Key details to include are:
- What you've accomplished since your previous milestone
- What your biggest challenges and triumphs were at BSE
- A summary of key topics you learned about
- What you hope to learn in the future after everything you've learned at BSE

For my final milestone, I created the carbon fiber belt, then put everything together. A major challenge I faced during this milestone was the fact that one of my sensors broke and provided false readings, meaning I had to redo the circuit. 


# Final Milestone Images
Tinkercad model of a slide buckle from the gallery  
<img width="572" height="387" alt="image" src="https://github.com/user-attachments/assets/343027a4-8402-4b53-bad3-6cef7c388d2b" />  
*NOTE: My 3D printed buckle closed fine but now the pieces are stuck together, I didn't use the buckle because I got more velcro.*  
Carbon fiber belt with angled circuit attached to it  
<img width="400" height="244" alt="unnamed (8)" src="https://github.com/user-attachments/assets/ebb4c0ca-a9a2-40b7-ab59-9724be6a96a0" />  



# Second Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/0vOc4PQThgg?si=_IhgSQ82rfejddvE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

For my second milestone, I designed the layout of where each component I created would go on the carbon fiber vest I would make. During this process, I also 3D printed circuit boxes for ease of gluing each circuit to foam pads (that would be glued onto the carbon fiber). I then hot glued the circuits onto the carbon fiber vest

# Second Milestone Images
Schematics for attaching circuits to carbon fiber (to be worn like shown)  
<img width="300" height="300" alt="unnamed (4)" src="https://github.com/user-attachments/assets/52d7b971-b9b2-4fa6-8a67-433570192ab1" />  
Circuits + circuit boxes attached to foam pads  
<img width="300" height="300" alt="unnamed (3)" src="https://github.com/user-attachments/assets/c2c9c85c-b16c-4ebd-a0f2-7ad14e73316c" />  
3D printed angled circuit box demonstration  
<img width="300" height="300" alt="unnamed (5)" src="https://github.com/user-attachments/assets/cca0a0b0-0bef-489c-b8c0-cdd0888a5400" />  
Roll of carbon fiber from Amazon  
<img width="300" height="300" alt="unnamed (7)" src="https://github.com/user-attachments/assets/531f6f33-1b24-438e-9f12-57cb6a24706f" />

Foam padded circuits attached to vest  
<img width="300" height="300" alt="1087" src="https://github.com/user-attachments/assets/9d66c3f5-fe8a-4180-b0b0-1ef80394ec4a" />











# First Milestone


<iframe width="560" height="315" src="https://www.youtube.com/embed/l2qdgorQM70?si=HQVQbwGHnPglnoqT" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>  


For my first milestone, I breadboarded a circuit that uses an ultrasonic sensor, buzzer, and pro micro board. I then wrote code for the circuit to buzz/beep at frequencies directly proportional to the distance an object is calculated to be from the buzzer. This warns visually impaired people about obstacles in front of their body, as well as telling them the severity of their potential collision.

Right now, I have one of the four sensor-buzzer-circuits for my project.

To complete the project, I must design where this circuit goes on a jacket/carbon fiber sheet, then actually obtain and cut out the carbon fiber, and then attach the various parts onto the carbon fiber vest and belt.

Some challenges I faced during the first milestone were a faulty breadboard that required lots of debugging to discover, alongside compatability issues between my chromebook and the pro micro board. These connectivity issues were solved when I used my Windows laptop and the offline arduino IDE rather than chromebook and arduino cloud IDE. 

# First Milestone Images
First sensor circuit iteration (Breadboard didn't work)  
<img width="300" height="300" alt="First iteration of sensor circuit" src="https://github.com/user-attachments/assets/b3e93e39-5440-43da-8568-75c1835a48b2" />  
Second sensor circuit iteration (Working)  
<img width="300" height="300" alt="1047" src="https://github.com/user-attachments/assets/ac43efb1-47c1-4283-91ac-f7ad0df3dac9" />  
Two soldered-to-perfboard circuits  
<img width="300" height="300" alt="613837293-d0801220-992b-4303-ad26-2289bcae95bd" src="https://github.com/user-attachments/assets/2955414a-123d-482d-8672-03de137cecd1" />  

Second circuit wiring adjustments for tactile feedback  
<img width="300" height="350" alt="unnamed (2)" src="https://github.com/user-attachments/assets/54dadf02-5499-49a9-bfd2-b787fcaed53e" />  



# Schematics 
Milestone 1 Circuit Diagram with LED rather than buzzer for visual response (ease of debugging)  
<img width="490" height="290" alt="image" src="https://github.com/user-attachments/assets/768dcc3c-f00b-452f-8e8b-f1b53e2bffa7" />


# Code

Code with the Arduino IDE  

```c++
/* Code to make buzzer buzz at various frequencies based on calculated distance of an object from sensor
 */
const int trigPin = 14; //set variables as pin numbers for less confusion/magic numbering + ease of changing
const int echoPin = 15;
const int buzz = 16;
float cm,duration;

int delaylay;

void setup() { //just setup and begin rate of Serial to match with monitor
  
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  pinMode(buzz,OUTPUT);
  Serial.begin(9600);
    
}

void loop() {
 //digitalWrite(buzz,HIGH);
 //y(2000);
  digitalWrite(trigPin, LOW);//start of the loop sends out a short 10-microsecond pulse of noise
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  //Serial.println("Sent signal");
  
  duration = pulseIn(echoPin, HIGH,30000); /*the echo pin is set to High upon the exit of the sound wave, and starts measuring once it is set to High. When the echo pin recieves the noise that was sent, it switches to low and the pulseIn function records the time period between High to Low states in microseconds*/
  cm = (duration * 0.0343)/2; //conversion of speed of sound to cm/microsecond, to multiply it by duration multiseconds for distance
  if (cm <= 150 && cm > 2){
    delaylay = map(cm,2,150,50,800);
    //Serial.println("Got past setting delay");
    digitalWrite(buzz, HIGH);
    delay(20);
    digitalWrite(buzz,LOW);
    delay(delaylay);
    Serial.println(String(cm));
    //Serial.println("Buzzed" + String(cm));

  }
  else{
    digitalWrite(trigPin, LOW);//set to low to ensure it is at low
    delay(60);//to manage the rate at which sensor shoots sound when the object is out of it's range (prevent overheating)
    digitalWrite(buzz,LOW);//turn off buzzer preventing continuous buzzer noise (active buzzer is toggle)
  }
  
  
    
}

```

*NOTE: The code for the vibration motor circuits varies in the fact that it sets PIN 16 to HIGH for 150 milliseconds rather than 10 milliseconds. This is so the weight in the motor is spun for long enough that it shakes the motor and produces vibration.*

# Challenges
For the second circuit created, the vibration motor to provide tactile rather than audible feedback was not working very well, most likely due to bad soldered connections. After testing if the motor worked and resoldering some joints for better connectivity, the motor worked. However, the strength of the motor wasn't enough to get the wearer's attention, so I moved on to CADing circuit boxes for the two components I made and ordering materials. Afterwards, I found out my vibration motor circuit had a code issue and made the period at which the motor vibrates longer than the period the buzzer would take to beep (I recycled buzzer code for motor code). It turns out that I was right, so now the motor both works consistently and produces enough of a vibration to be felt through cloth (the earlier period for the buzzer wasn't long enough for the motor to get spinning if the distance was past a certain point because of the added delay).
# Bill of Materials
Here's where you'll list the parts in your project. To add more rows, just copy and paste the example rows below.
Don't forget to place the link of where to buy each component inside the quotation marks in the corresponding row after href =. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize this to your project needs. 

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| Jecery Carbon Fiber Sheet (6.5 ft by 12") (Black) | What the item is used for | $16.90 | <a href="https://www.amazon.com/Carbon-Structural-Reinforcement-Concrete-Basements/dp/B0BCNQXN7D/ref=sr_1_3?dib=eyJ2IjoiMSJ9.5jhn41WqYeKujVHiGVecwfkUfqQYYbgRIF7WNXmjvuixjSs6XK_rkHeXjqVV6KR7jWmVBuqd1z1vGzuOBVala5uGrbrZspjYq1LmIVYrKJ2a8iz4fjRGoZ16H16Ucagkj_aDye1qjrMld7lEz7vm486fsrOY503VmtlC3Ys-3TgbdoVG2bUF6six9Im2xtESyfnQU6AhL6hVeKqczENSduKy2Q6TdgROQ8uLklCwiDw.cgT39aujoABoP_FB11y_cl7YQIAcMU8uS1cb3b2_7Bc&dib_tag=se&keywords=fiber%2Bsheet&qid=1782257577&sr=8-3&th=1"> Link </a> |
| Arduino Pro Micro x 3 | Programmed to send power to pins under certain conditions via Arduino IDE | $22.50 x 3 | <a href="https://www.sparkfun.com/pro-micro-5v-16mhz.html?srsltid=AfmBOoreT8dJajXIeMY9PkLlnRz7L14C2gg2fORkX-7eIy5m_sGlBzjY"> Link </a> |
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |

# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)

To watch the BSE tutorial on how to create a portfolio, click here.
