
# Assistive Smart Jacket

Sensors that send out sound and record the time it takes for the sound waves' echoes to return to said sensors. The time recorded can be used to find the distance an object is from the sensor in the direction of the emitted sound. When the distance of an object from the sensor passes a certain threshold, buzzers are triggered (faster frequency corresponds with closer distance). 


You should comment out all portions of your portfolio that you have not completed yet, as well as any instructions:
```HTML 
<!--- This is an HTML comment in Markdown -->
<!--- Anything between these symbols will not render on the published site -->
```

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



# Second Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/y3VAmNlER5Y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your second milestone, explain what you've worked on since your previous milestone. You can highlight:
- Technical details of what you've accomplished and how they contribute to the final goal
- What has been surprising about the project so far
- Previous challenges you faced that you overcame
- What needs to be completed before your final milestone 

# First Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/CaCazFBhYKs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your first milestone, describe what your project is and how you plan to build it. You can include:
- An explanation about the different components of your project and how they will all integrate together
- Technical progress you've made so far
- Challenges you're facing and solving in your future milestones
- What your plan is to complete your project

For my first milestone, I breadboarded a circuit that uses an ultrasonic sensor, buzzer, and pro micro board. I then wrote code for the circuit to buzz/beep at frequencies directly proportional to the distance an object is calculated to be from the buzzer. This warns visually impaired people about obstacles in front of their body, as well as telling them the severity of their potential collision.

To complete the project, I must design where this circuit goes on a jacket/carbon fiber sheet, then actually obtain and cut out the carbon fiber, and then attach the various parts onto the carbon fiber vest and belt.

Some challenges I faced during the first milestone were a faulty breadboard that required lots of debugging to discover, alongside compatability issues between my chromebook and the pro micro board. These connectivity issues were solved when I used my Windows laptop and the offline arduino IDE rather than chromebook and arduino cloud IDE. 

# First Milestone Images
First sensor circuit iteration (Breadboard didn't work)  
<img width="300" height="300" alt="First iteration of sensor circuit" src="https://github.com/user-attachments/assets/b3e93e39-5440-43da-8568-75c1835a48b2" />  
Second sensor circuit iteration (Working)  
<img width="300" height="300" alt="1047" src="https://github.com/user-attachments/assets/ac43efb1-47c1-4283-91ac-f7ad0df3dac9" />


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
  
  duration = pulseIn(echoPin, HIGH,30000);/*the echo pin is set to High upon the exit of the sound wave, and starts measuring once it is set to High. When the echo pin recieves the noise it sent, it switches to low and the pulseIn function records the time period between High to Low in microseconds*/
  cm = (duration * 0.0343)/2;//conversion of speed of sound to cm/microsecond, to multiply it by duration multiseconds for distance
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

# Bill of Materials
Here's where you'll list the parts in your project. To add more rows, just copy and paste the example rows below.
Don't forget to place the link of where to buy each component inside the quotation marks in the corresponding row after href =. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize this to your project needs. 

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |

# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)

To watch the BSE tutorial on how to create a portfolio, click here.
