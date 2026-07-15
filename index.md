# Self Driving Car
Intially I started my experience at BlueStamp with a small-scale starter project called the Jitterbug, through this I learned how to feed solder, heat a joint and create solid electrical connections on a circuit board. Additionally I was exposed to different components like LEDs, switches, battery holders and a vibration motor. After gaining some experience with some basic engineering components I began with my chosen intensive project, the self driving car, which is essentially an autonomous scale vehicle controlled by an Arduino microcontroller. It utilizes LEDs and three different sensors, the line tracker, obstacle avoidance and ultrasonic to scan its surroundings, detect lanes and potential obstacles. By writing custom code I programmed the robot to automatically steer, map its distance to avoid collisions and calibrate its sensors to filter out noise and false readings which may be disruptive to the movement of the car.


| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:---:|:---:|:---:|:---:|
| Saadhana R | Emerald High | Mechanical Engineering | Incoming Junior |

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

Assembly and autonomy:
The self driving car uses a 9V battery to power its motors attached to the bottom as well as the arduino microcontroller, the obstacle avoidance and ultrasonic sensors are wired to the breadboard and pins on the arduino in order for it to function. So far, I have created the basic structure of the car, secured the motors and chassis and wired the two main sensors to the microcontroller and programmed the car to detect lanes, scan its surroundings and operate safely by avoiding collisions. Some challenegs I've faced regard the line tracking sensor overheating, code malfunctioning causing the car to move abruptly and the car moving slowly due to the battery not providing sufficient power to the arduino and 2 DC motors. My plan to complete the project is to incorporate sensor fusion logic into my code, install a back camera to elevate my vehicle into a true smart car, implement speed adjustments using calibration to establish full control and start focusing on potential modifications.


# Schematics 
Here's where you'll put images of your schematics. [Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser. 

# Code
Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs. 

```c++
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  Serial.println("Hello World!");
}

void loop() {
  // put your main code here, to run repeatedly:

}
```

# Bill of Materials
Here's where you'll list the parts in your project. To add more rows, just copy and paste the example rows below.
Don't forget to place the link of where to buy each component inside the quotation marks in the corresponding row after href =. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize this to your project needs. 

| **Part** | **Note** | **Price** | **Link** |

| Controller Board (Arduino UNO) | Microcontroller/brain of the vehicle | $22 | [ https://www.amazon.com/Arduino-UNO-Minima-ABX00080-Connector/dp/B0C78K4CD4/ref=sr_1_9?crid=3CSXMT8R28H7R&dib=eyJ2IjoiMSJ9.fHcHTxEwj7lDGrApysBpHk8QzLINAYGbhDZ9uBCi-pM9wdH2GQTLBipWw6K1q3uOfWOvhlWoBTAJQ5XO2BmGLyghdwI_HRHs2ZwAHri2dlicJdkLxk1QXjIiRaCz3VYXqG_pxa1F859BNL-sqlL9XtdqsV_oH9XOuMt2dFZdtK6hpu3d-AHa_ZOyYs-IscWM10jy3nVRPVswH_4LXmiJFyDITRwxbM5_ntMuCZ-5nro.mWGkqKpOWCfp2dXuAHDUiachz8KveH14L4uT05ozeXY&dib_tag=se&keywords=arduino+microcontroller&qid=1784148851&sprefix=arduino+microcontroller+%2Caps%2C177&sr=8-9 ] |

| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
| Item Name | What the item is used for | $Price | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |

# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)

To watch the BSE tutorial on how to create a portfolio, click here.
