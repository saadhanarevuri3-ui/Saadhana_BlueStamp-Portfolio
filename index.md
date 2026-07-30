# Self Driving Car
I engineered and built a small-scale prototype capable of real-time obstacle avoidance and lane changing by using its headlights as indicators. The car is powered by an Arduino UNO board which powers the OLED Display module. The system essentially integrates ultrasonic distance tracking, infrared proximity-sensing and line tracking logic to scan its surroundings and move accordingly.


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

<iframe width="560" height="315" src="https://www.youtube.com/watch?v=7EZxqqa1bf8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

Sensor Fusion and Motor Driver Optimization:
For the second stage of my project I focused on implementing advances sensor logic which combines data from the different sensors to create one accurate and reliable view of the environment, and fine-tuning the vehicles driving behavior to ensure stable navigation. Initially, I incorporated sensor fusion logic into my existing code using three independent sensors, line tracking, infrared and ultrasonic. With this combined real-time data the car can track obstacle distance while simultaneously avoiding any objects it comes in close contact to laterally on the left and right, the code basically executes immediate swerving maneuvers or reversing. In addition, I installed LED headlights using electrical tape, positioning them carefully out of sight so they wouldn't interfere with the ultrasonic or IR sensors. In this part of the process I focused mainly on the hardware of the LEDs leaving the coding and building the circuit as a next step. While I initially experimented with a serial-controlled lane changing feature, I later diverted my time and energy towards perfecting the autonomous steering logic because real-time navigation proved more critical to the car's performance.

Challenges:
The most significant hurdles to overcome during this milestone were motor channel and direction mapping, within the code there were swaps between Motor A and Motor B as well as flipped pin direction configurations. These issues caused the car to twitch, move backward and even reverse when encountering obstacles instead of making smooth turns like it was programmed to. I also ran into friction and voltage issues where the two motors required drastically different power levels to spin at the same speed. I resolved this by implementing minimum PWM thresholds while constraining values to prevent overflowing of the 8-bit limit. Working on a smaller breadboard made wiring so many connections chaotic. The overcrowded jumper wires made it difficult to wire the RGB LEDs I had originally planned to since they not only took up space on the breadboard but there also weren't enough digital pins on the Arduino. To combat this challenge I resorted to using regular LEDs which had only two legs, the cathode and anode, this made the circuit much less complicated and took up only 4 pins on the breadboard. Due to the shortage of digital pins on the Arduino UNO board, I ended up using 2 analog pins to control the LEDs which leaves just enough room for my next step which includes installing and mounting an OLED Display Module which can be programmed and wired to show the car's status. 

<img width="3024" height="4032" alt="IMG_3951" src="https://github.com/user-attachments/assets/4ee3a10e-715e-4e75-be60-53d15542f09d" />

Lessons Learned:
When adjusting the speeds of Motors A and B I realized that code logic that makes sense mathematically, such as setting a motor to 25% power doesn't actually translate to physical hardware. While testing the amount of volts being supplied to Motor A with a multimeter I found out that it was a battery issue since one motor had a higher voltage than the other. After replacing the battery I proceeded to strengthen the soldered connections on the slower motor by pressing one joint firmly until the wheel was spinning in perfect sync with the other. While troubleshooting it became clear that every motor has a minimum stall threshold that must be accounted for in software and hardware. As for the ultrasonic module, rapid sensor reads can cause severe issues in execution or jittery motor behavior. Timing loops ensure that sensors don't freeze or cause sudden changes in speed, so ultimately non-blocking logic is essential. Lastly, clean wire management isn't just about appearance, lose wires hanging over optical or IR sensors can introduce obstacles that are difficult to trace in code.

<img width="3024" height="4032" alt="IMG_3952" src="https://github.com/user-attachments/assets/4ddb9d6e-b4ca-4bfe-a98c-81618808693d" />

# First Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/CaCazFBhYKs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

Assembly and autonomy:
The self driving car uses a 9V battery to power its motors attached to the bottom as well as the Arduino microcontroller, the obstacle avoidance and ultrasonic sensors are wired to the breadboard and pins on the Arduino in order for it to function. So far, I have created the basic structure of the car, secured the motors and chassis and wired the two main sensors to the microcontroller and programmed the car to detect lanes, scan its surroundings and operate safely by avoiding collisions. Some challenges I've faced regard the line tracking sensor overheating, code malfunctioning causing the car to move abruptly and the car moving slowly due to the battery not providing sufficient power to the Arduino and 2 DC motors. My plan to complete the project is to incorporate sensor fusion logic into my code, install a back camera to elevate my vehicle into a true smart car, implement speed adjustments using calibration to establish full control and start focusing on potential modifications.

Challenges


# Schematics 
Motor driver:
<img width="743" height="462" alt="Screenshot 2026-07-21 at 2 31 19 PM" src="https://github.com/user-attachments/assets/2c43065b-0d76-46d7-b950-2fc6a93747a9" />

IR sensors:
<img width="749" height="745" alt="Screenshot 2026-07-21 at 2 59 25 PM" src="https://github.com/user-attachments/assets/040f1791-0414-4ed1-9a3c-5d37e5b53fff" />

LEDs (Headlights) and OLED display module:
<img width="801" height="464" alt="Screenshot 2026-07-28 at 10 24 42 PM" src="https://github.com/user-attachments/assets/3f42fa15-84ec-483e-9ef6-ae4d50f457ac" />
 

# Code
#include <Wire.h>
#include <Adafruit_GFX.h>
#include <Adafruit_SSD1306.h>

#define SCREEN_WIDTH 128
#define SCREEN_HEIGHT 64
#define OLED_RESET -1
#define SCREEN_ADDRESS 0x3C

Adafruit_SSD1306 display(SCREEN_WIDTH, SCREEN_HEIGHT, &Wire, OLED_RESET);

const int A_1B = 5;
const int A_1A = 6;
const int B_1B = 9;
const int B_1A = 11;

const int MOTOR_A_BOOST = 100;

const int lineTrack = 2;
const int echoPin   = 4;
const int trigPin  = 12;
const int rightIR  = 7;
const int leftIR   = 8;

const int leftHeadlight  = A3;
const int rightHeadlight = A2;

const int CRUISE_SPEED = 140;
const int TRACK_SPEED  = 130;

unsigned long lastDisplayTime = 0;
const unsigned long DISPLAY_INTERVAL = 250;

int getMotorASpeed(int baseSpeed) {
  return constrain(baseSpeed + MOTOR_A_BOOST, 0, 255);
}

void setup() {
  Serial.begin(9600);

  Wire.begin();
  if (!display.begin(SSD1306_SWITCHCAPVCC, SCREEN_ADDRESS)) {
    for (;;);
  }

  display.clearDisplay();
  display.setTextSize(1);
  display.setTextColor(SSD1306_WHITE);
  display.setCursor(10, 20);
  display.println(F("SYSTEM READY"));
  display.setCursor(10, 35);
  display.println(F("SWERVE BALANCED"));
  display.display();
  delay(1000);

  pinMode(A_1B, OUTPUT);
  pinMode(A_1A, OUTPUT);
  pinMode(B_1B, OUTPUT);
  pinMode(B_1A, OUTPUT);

  pinMode(lineTrack, INPUT);
  pinMode(echoPin, INPUT);
  pinMode(trigPin, OUTPUT);
  pinMode(leftIR, INPUT);
  pinMode(rightIR, INPUT);

  pinMode(leftHeadlight, OUTPUT);
  pinMode(rightHeadlight, OUTPUT);
  digitalWrite(leftHeadlight, HIGH);
  digitalWrite(rightHeadlight, HIGH);

  stopMove();
}

void loop() {
  int leftObstacle  = digitalRead(leftIR);
  int rightObstacle = digitalRead(rightIR);
  float distance    = readSensorData();

  if (millis() - lastDisplayTime >= DISPLAY_INTERVAL) {
    lastDisplayTime = millis();
    updateOLED(distance, leftObstacle, rightObstacle);
  }

  if (leftObstacle == LOW && rightObstacle == LOW) {
    moveBackward(TRACK_SPEED);
  }
  else if (distance < 25.0 && distance > 2.0) {
    stopMove();
    delay(50);

    unsigned long reverseStart = millis();
    while (millis() - reverseStart < 400) {
      moveBackward(TRACK_SPEED);
    }

    stopMove();
    delay(50);

    leftObstacle  = digitalRead(leftIR);
    rightObstacle = digitalRead(rightIR);

    if (leftObstacle == LOW) {
      backLeft(TRACK_SPEED);
    } else {
      backRight(TRACK_SPEED);
    }
    delay(400);
  }
  else if (leftObstacle == LOW && rightObstacle == HIGH) {
    backLeft(TRACK_SPEED);
  }
  else if (leftObstacle == HIGH && rightObstacle == LOW) {
    backRight(TRACK_SPEED);
  }
  else {
    moveForward(CRUISE_SPEED);
  }
}

void moveForward(int speed) {
  analogWrite(A_1B, 0);
  analogWrite(A_1A, getMotorASpeed(speed));
  analogWrite(B_1B, 0);
  analogWrite(B_1A, speed);
}

void moveBackward(int speed) {
  analogWrite(A_1B, getMotorASpeed(speed));
  analogWrite(A_1A, 0);
  analogWrite(B_1B, speed);
  analogWrite(B_1A, 0);
}

void backLeft(int speed) {
  analogWrite(A_1B, 0);
  analogWrite(A_1A, getMotorASpeed(25));
  analogWrite(B_1B, 0);
  analogWrite(B_1A, speed);
}

void backRight(int speed) {
  analogWrite(A_1B, 0);
  analogWrite(A_1A, getMotorASpeed(speed));
  analogWrite(B_1B, 0);
  analogWrite(B_1A, 80);
}

void stopMove() {
  analogWrite(A_1B, 0);
  analogWrite(A_1A, 0);
  analogWrite(B_1B, 0);
  analogWrite(B_1A, 0);
}

float readSensorData() {
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  long duration = pulseIn(echoPin, HIGH, 18000);

  if (duration == 0) {
    return 999.0;
  }

  return duration / 58.00;
}

void updateOLED(float dist, int lIR, int rIR) {
  display.clearDisplay();
  display.setTextSize(1);
  display.setTextColor(SSD1306_WHITE);
  display.setCursor(10

# Bill of Materials
Here's where you'll list the parts in your project. To add more rows, just copy and paste the example rows below.
Don't forget to place the link of where to buy each component inside the quotation marks in the corresponding row after href =. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize this to your project needs. 

| **Part** | **Note** | **Price** | **Link** |

| Controller Board (Arduino UNO) | Microcontroller/brain of the vehicle | $22 | <a href="https://www.amazon.com/Arduino-UNO-Minima-ABX00080-Connector/dp/B0C78K4CD4/ref=sr_1_9?crid=3CSXMT8R28H7R&dib=eyJ2IjoiMSJ9.fHcHTxEwj7lDGrApysBpHk8QzLINAYGbhDZ9uBCi-pM9wdH2GQTLBipWw6K1q3uOfWOvhlWoBTAJQ5XO2BmGLyghdwI_HRHs2ZwAHri2dlicJdkLxk1QXjIiRaCz3VYXqG_pxa1F859BNL-sqlL9XtdqsV_oH9XOuMt2dFZdtK6hpu3d-AHa_ZOyYs-IscWM10jy3nVRPVswH_4LXmiJFyDITRwxbM5_ntMuCZ-5nro.mWGkqKpOWCfp2dXuAHDUiachz8KveH14L4uT05ozeXY&dib_tag=se&keywords=arduino+microcontroller&qid=1784148851&sprefix=arduino+microcontroller+%2Caps%2C177&sr=8-9"> Link </a> |

| L9110 Motor Driver module | Serves as a h-bridge to power TT motors | $3.50 | <a href="https://www.amazon.com/VKLSVAN-H-Bridge-Channel-Stepper-Controller/dp/B0DQPRLTBD/ref=sr_1_5?crid=XOZ96K34FEGR&dib=eyJ2IjoiMSJ9.OmcelklwhMk2imYeBvDNU1PmbHE7WDakRl-A7eVTafSE3dysT5EFFUNQVg_Qoj8d_PLXgPYsko8U50Pkio1gtRW-qlCvu7NVVw7Bhp6yG8qJY20BL6N8DpqKYv7fl9afpRRJqBGpawdp0NquuVIMLrTNnngXismliee7k8QZx8PR-M_aKQvotXMWSxNQYkUb8z_SOVucgB7wKhqCCiwjwnYdCIlOuDT6aOaHaV6Detk.Q2kBf3tuM5eNn3a2bX0gCyLJvsY18DvlxuTgnknknbQ&dib_tag=se&keywords=L9110%2Bmotor%2Bdriver%2Bmodule&qid=1784149455&sprefix=l9110%2Bmotor%2Bdriver%2Bmodule%2Caps%2C185&sr=8-5&th=1"> Link </a> |

| TT Motors (2) | Drives the wheels | $2.50 | <a href="https://www.amazon.com/D-FLIFE-Motor-Gearbox-200RPM-Ratio/dp/B0C3LYZHB8/ref=sr_1_12?crid=29ZRGCG7OMV1N&dib=eyJ2IjoiMSJ9.VFvmjZ6X2lLerHG6wM2_Zwfl36qWgxmR6GprDkLz018fyZvGDUxw4b-rXarsYsg0TY3iSLDHXBHXXHesADH8CJu9zxrte2uQFG2QR4PQYeXWngLdJqRpmgp54ZMRnWqqj4l1ByYsv-2ACZULvVz18rUmz4nxWuV7W9Dy9i51PZlLTugjKRHp10WV4Q8o589AUVi3QZNfc4S667CK7RKy67Defd_YVLiBCGknBHRayv_erNhmayVSQtAKpHn2diKuMipnZkKVxTbOyZSkS2-7g3djNDljy-ciBh45maUXqxo._UfZChBjIba-YCFn6ew4CnqDYe2ypYr32-KU4OcZNMY&dib_tag=se&keywords=TT+motors&qid=1784149613&sprefix=tt+motor%2Caps%2C236&sr=8-12"> Link </a> |

| TT Wheels (2) | Used for movement of the car | $2 | <a href="https://www.amazon.com/4Pcs-TT-Motor-Wheels-Replacement/dp/B0GFNFQNHX/ref=sr_1_6 crid=G3DUE7KM4GTI&dib=eyJ2IjoiMSJ9.0bmLnlgPNfl5m7xj_fOI1tg8lcUG2osMjQ57kyahnnn0ORZEFX1k1ZZ5uB01svvJauZPfdCwmTy6_cAlbrWC1D_ELe3PIj53t98jmvcvllyvcL7DWDwGCV4YJ1QhXebwCwgpoPyR97TVbAS2hZp5o6apuT8RPRzdfcGAazzmyf9OV_lbDbY5L8Vp11iR5Oc3o2926XcW_IO2BWNAiBnCc3qztY7dcj_FlyYgQJkma1s7kLeRHYeyYvij-jZvZudY-pxnr8BkRIYvDK9j_2O6PjWcZIiiC7MP9Mh1ybEb-M0.gLefMo7IR-_nIu2aJ8NHmkkgDTER3EmigNGkVOr8zuQ&dib_tag=se&keywords=TT+wheels&qid=1784149699&sprefix=tt+wheels%2Caps%2C165&sr=8-6"> Link </a> |

| 1'' Universal Wheel | Allows free pivoting | $1.50 | <a href="https://www.amazon.com/Luomorgo-inch-Swivel-Caster-Wheels/dp/B07GLPJJ7D/ref=sr_1_4?crid=3JCXCAEZWRBRW&dib=eyJ2IjoiMSJ9.uIOC75avVCdhal7Qt9VzKGilQ0LamE3c_urBMDSAIz7fzPGNoTr7ahJCz21XbUurorYn4S2nbPF_VtmDua06LaO9I_cMIVx7tlJVutAF3G4-RmlPvPHYUCRQWSFh31SciV-Y3HFVRsyUvwKzw4ktyk1Rbx0V6cWXM0ATsDUcAZ6K_IsfS-Z2DuNAsiBbIIQkn_dfwdPP9PvnKT4QX_8ALBkhzHGiW59Ciu5SFyHCxhs.y-eeQFB1C0cjdBMzQpLN4GfM6AKNbcvxvyFCeX0f-JU&dib_tag=se&keywords=1%27%27+universal+wheel&qid=1784149775&sprefix=1%27%27+universal+wh%2Caps%2C380&sr=8-4"> Link </a> |

| Ultrasonic sensor (HC-SR04) | Measures distance to objects directly in front | $4 | [https://www.amazon.com/WWZMDiB-HC-SR04-Ultrasonic-Distance-Measuring/dp/B0B1MJJLJP/ref=sr_1_3?crid=1XU51UGEJZZA&dib=eyJ2IjoiMSJ9.w-v74CMMP9eRh1BFF5BJ6xZlNH9LlX5HLX1Axp43FWYbpT_9h64LVT_hJcnFuLLU36s_1nGWoajK4N7MDmpkDbi2FD493Elxaym8UiH6arIe__PyXoq2LX7aqWpugzEO_DIOOE9O7vX_HJ8QIcJM-abGJFBGgxymELZqei_ECXRUWStpf-xokFMdnW2nMLgXaezf5zO9rvQcVLcFnicIB3Dl1lj33dbwYedAZPhl-Ik.3z9_LFUevjzpp-SKwPtmU7DxTibRFMN71Wcl6_aEQcs&dib_tag=se&keywords=ultrasonic%2Bsensor&qid=1784149948&sprefix=ultrasonic%2Bsensor%2Caps%2C172&sr=8-3&th=1] |
| IR obstacle avoidance sensors (2) | blind-spot detection | $2 | [https://www.amazon.com/Infrared-Avoidance-Transmitting-Receiving-Photoelectric/dp/B07PFCC76N/ref=sr_1_1_sspa?crid=1W5YFEYDI0TAN&dib=eyJ2IjoiMSJ9.AJ7Iwf87FduxzumjewKRxOmAi5Xj-dzRvvie66VtEjUUjJebZH84qJULVAep8bvjWIcJR2oe-9FJR8ISCxhgWZQwpoty4VFxdP3tR9nRl8F3o3cMreO_A9XCIcMVBg_JRK5hOp7hCcDnv139IADr-5_BOPE4Uq3DqQnUx7HJNTwxifXDAjcI7ucF9hpBmg4e47m7CsnKqfHjZ-1YEvrtV013Dl0Pj6NCSRrbcn3oa3M.6WuBqFHwK1_k9f3orEyMkvqrGOmmh38hm4BqnVZGnF0&dib_tag=se&keywords=ir%2Bobstacle%2Bavoidance%2Bsensor&qid=1784150037&sprefix=IR%2Bobstacle%2B%2Caps%2C158&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1] |
| Line Tracking sensor | detects high-contrast lane lines | $3 | [https://www.amazon.com/DAOKAI-1-Channel-Detection-Adjustable-Sensitivity/dp/B0BGYCZ8HV/ref=sr_1_4?crid=H1B0FAN2K89E&dib=eyJ2IjoiMSJ9.1OTPBSu98Sl867yOWO1flCILllw-0QqZtvZp3D8si2Kz1WSgKb4_d-sLOyanwLVDw77BkIZvPUzpY1jlj4geTm_jHJPNcWkJOSKRjr4Qkm7qiG59ZVwwA80TGFBJ2b1LxC9eyqRMslE05dL6EMA8QXS1Ic-b25xMAZa78AiXk0SQ8wGRYsgZybUFH4QKe67NbFriL1-fC9OcKObXPRRMAJE3SpExC9x_05BijchnwMc.sTi-PGZp0xF-08jSzn9W3Pa-0YpPqzdjWFZPFsJV608&dib_tag=se&keywords=line+tracking+sensor&qid=1784150157&sprefix=line+tracking+sensor%2Caps%2C221&sr=8-4] |
| RGB LEDs | Headlights communicating car's thinking | $1 | [https://www.amazon.com/Tricolor-Multicolor-Lighting-Electronics-Components/dp/B01C19ENFK/ref=sr_1_1_sspa?crid=1UH5PDO416YCP&dib=eyJ2IjoiMSJ9.BU4S0jVgvYFMaG3YX-8kv5g7mf-L7uSxfBvlcMa27TJ1IcyxNEUDHRcL-zCrf9taKn7gLzVMNdvy_gL4fTwFJKmGSUBJgakKHw3QBUgEA_rVF39r54SIFdE1wm14koM_xk0P2ebif6AHtdLXjbnXZLYJLDm41J-7Ras9nPEgaT76JTi2zYJQdkjuF0TbxoiPpMVQyw1-t38F1TzubAEUF8ZNE3OLj_eFGzmAovrfuaw.32ZuAA9otDqRrSfna6Yk4gSJv7bQJfL_sq-7c_leNXQ&dib_tag=se&keywords=RGB%2BLEDs&qid=1784150277&sprefix=rgb%2Bleds%2Caps%2C170&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1] |
| Mini breadboard | Distributes power to sensors and modules | $4 | [https://www.amazon.com/WWZMDiB-SYB-170-Breadboard-Plates-Multicolored/dp/B09YXQJMTG/ref=sr_1_1_sspa?crid=3MIJBKTKZTM3S&dib=eyJ2IjoiMSJ9.EQvCK09g_r0CejNbKABqFd6BZTf9pk6ztW2A000LkgvEt1uWVaC2byg0yHEhZqN-wzEYuDcVUCub58HrMcW9ODMdBF6paEFM6UeWIYLGYMqaL1gUy5LFXQP_WY6Nij-cANoSDVJCkX8DshniMZrE9Pb8TZKApd5A_szF8LlrToq-ttrPjSTO9pZp2G-D1Mv-PLzqmasLp4fzrEZXF3XReMW417_J6BfRORaHT-l0B1k.9WdNUTzZ8T2nKgcnpl3wboRahooREl3aFexta-No4CE&dib_tag=se&keywords=mini+breadboard&qid=1784150336&sprefix=mini+breadboar%2Caps%2C169&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1] |
| Car chassis (Sunfounder Kit) | Main mounting platform | $8 |[https://www.amazon.com/SunFounder-Ultimate-Tutorials-Beginners-Enthusiasts/dp/B0CGJ235XN/ref=sr_1_2_sspa?crid=2X74H3K1NMXVA&keywords=car+chassis+from+sunfounder&qid=1784150435&sprefix=car+chassis+from+sunfounde%2Caps%2C139&sr=8-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9tdGY&psc=1]|
| 9V Battery and clip cable | Portable power source | $4 | [https://www.amazon.com/PKCELL-Alkaline-9V-Detector-Batteries/dp/B0DG4QRJKQ/ref=sr_1_3_sspa?crid=1JALRZDVI4DBH&dib=eyJ2IjoiMSJ9.UTIEEJxrXzAacW7rXzP5baUO2v4AozDKVKm1_F2qlZHQ9hVteUKkel2la7e8OJUgaikzHh0dHlxqJbmWwF4VZwtJwmZD0QQTlisQcO7F_0ae2tTcY7W0_7NWs1p9548IwNEybt0lYddqBe9wztucsnXaGewAnErwssdUTeBfFZTztlB0YP-Cf-LcQOZgsBZlSoEiU_gvvOWXL3pLg1zp-7XYtY-8AVi5YYcckODXgMWX6UuAcru0lH39HzFiNWx-t1RSKrQ76S3ogAPm1R9AoTC3gr68fsC_hVxN0Yxjq3c.ZJpFVctMqKGLrhFPOZKaAcEtlhqpZyZuqHRdK9TDGDg&dib_tag=se&keywords=9V+battery&qid=1784150561&sprefix=9v+battery+%2Caps%2C181&sr=8-3-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1] |
| Jumper wires | Physical electrical connections | $2 | [https://www.amazon.com/WWZMDiB-120Pcs-Multicolored-Breadboard-Jumper/dp/B0B2L66ZFM/ref=sr_1_1_sspa?crid=1X65CJJW2TMHZ&dib=eyJ2IjoiMSJ9.I3nSspk5onl8Jong0G-0EaUV8k3yvkfNxu9EofYJ660_GAukluqKFTDs3FZ9XfRKGf2JDS-z84NqDSzLJ-WDAORU4znBSUEQeeaFqHWUsrCKMwH6q3pCBe0rts-vP06Mx53JRw5NW485BUAZ8cw9vI9jP1ThUOfMIMZ4eqjNVDbUX6Yep-H49NldtvjWZVAC1LCxP-YzbV7rskmRBbaTRNeTvV9zw-QjPVzqoJPZQos.9ZzrhVo1c-tKddZRj9hYr2B53wN0nk_WwewtlmUXxxM&dib_tag=se&keywords=jump+wires&qid=1784150611&sprefix=jump+wire%2Caps%2C174&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1] |
