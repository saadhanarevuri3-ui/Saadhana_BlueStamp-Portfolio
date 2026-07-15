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

| Controller Board (Arduino UNO) | Microcontroller/brain of the vehicle | $22 | <a href="https://www.amazon.com/Arduino-UNO-Minima-ABX00080-Connector/dp/B0C78K4CD4/ref=sr_1_9?crid=3CSXMT8R28H7R&dib=eyJ2IjoiMSJ9.fHcHTxEwj7lDGrApysBpHk8QzLINAYGbhDZ9uBCi-pM9wdH2GQTLBipWw6K1q3uOfWOvhlWoBTAJQ5XO2BmGLyghdwI_HRHs2ZwAHri2dlicJdkLxk1QXjIiRaCz3VYXqG_pxa1F859BNL-sqlL9XtdqsV_oH9XOuMt2dFZdtK6hpu3d-AHa_ZOyYs-IscWM10jy3nVRPVswH_4LXmiJFyDITRwxbM5_ntMuCZ-5nro.mWGkqKpOWCfp2dXuAHDUiachz8KveH14L4uT05ozeXY&dib_tag=se&keywords=arduino+microcontroller&qid=1784148851&sprefix=arduino+microcontroller+%2Caps%2C177&sr=8-9"> Link </a> |
| L9110 Motor Driver module | Serves as a h-bridge to power TT motors | $3.50 | <https://www.amazon.com/VKLSVAN-H-Bridge-Channel-Stepper-Controller/dp/B0DQPRLTBD/ref=sr_1_5?crid=XOZ96K34FEGR&dib=eyJ2IjoiMSJ9.OmcelklwhMk2imYeBvDNU1PmbHE7WDakRl-A7eVTafSE3dysT5EFFUNQVg_Qoj8d_PLXgPYsko8U50Pkio1gtRW-qlCvu7NVVw7Bhp6yG8qJY20BL6N8DpqKYv7fl9afpRRJqBGpawdp0NquuVIMLrTNnngXismliee7k8QZx8PR-M_aKQvotXMWSxNQYkUb8z_SOVucgB7wKhqCCiwjwnYdCIlOuDT6aOaHaV6Detk.Q2kBf3tuM5eNn3a2bX0gCyLJvsY18DvlxuTgnknknbQ&dib_tag=se&keywords=L9110%2Bmotor%2Bdriver%2Bmodule&qid=1784149455&sprefix=l9110%2Bmotor%2Bdriver%2Bmodule%2Caps%2C185&sr=8-5&th=1> < Link > |
| TT Motors (2) | Drives the wheels | $2.50 | <https://www.amazon.com/D-FLIFE-Motor-Gearbox-200RPM-Ratio/dp/B0C3LYZHB8/ref=sr_1_12?crid=29ZRGCG7OMV1N&dib=eyJ2IjoiMSJ9.VFvmjZ6X2lLerHG6wM2_Zwfl36qWgxmR6GprDkLz018fyZvGDUxw4b-rXarsYsg0TY3iSLDHXBHXXHesADH8CJu9zxrte2uQFG2QR4PQYeXWngLdJqRpmgp54ZMRnWqqj4l1ByYsv-2ACZULvVz18rUmz4nxWuV7W9Dy9i51PZlLTugjKRHp10WV4Q8o589AUVi3QZNfc4S667CK7RKy67Defd_YVLiBCGknBHRayv_erNhmayVSQtAKpHn2diKuMipnZkKVxTbOyZSkS2-7g3djNDljy-ciBh45maUXqxo._UfZChBjIba-YCFn6ew4CnqDYe2ypYr32-KU4OcZNMY&dib_tag=se&keywords=TT+motors&qid=1784149613&sprefix=tt+motor%2Caps%2C236&sr=8-12> <Link> |
| TT Wheels (2) | Used for movement of the car | $2 | <https://www.amazon.com/4Pcs-TT-Motor-Wheels-Replacement/dp/B0GFNFQNHX/ref=sr_1_6?crid=G3DUE7KM4GTI&dib=eyJ2IjoiMSJ9.0bmLnlgPNfl5m7xj_fOI1tg8lcUG2osMjQ57kyahnnn0ORZEFX1k1ZZ5uB01svvJauZPfdCwmTy6_cAlbrWC1D_ELe3PIj53t98jmvcvllyvcL7DWDwGCV4YJ1QhXebwCwgpoPyR97TVbAS2hZp5o6apuT8RPRzdfcGAazzmyf9OV_lbDbY5L8Vp11iR5Oc3o2926XcW_IO2BWNAiBnCc3qztY7dcj_FlyYgQJkma1s7kLeRHYeyYvij-jZvZudY-pxnr8BkRIYvDK9j_2O6PjWcZIiiC7MP9Mh1ybEb-M0.gLefMo7IR-_nIu2aJ8NHmkkgDTER3EmigNGkVOr8zuQ&dib_tag=se&keywords=TT+wheels&qid=1784149699&sprefix=tt+wheels%2Caps%2C165&sr=8-6> <Link> |
| 1'' Universal Wheel | Allows free pivoting | $1.50 | [https://www.amazon.com/Luomorgo-inch-Swivel-Caster-Wheels/dp/B07GLPJJ7D/ref=sr_1_4?crid=3JCXCAEZWRBRW&dib=eyJ2IjoiMSJ9.uIOC75avVCdhal7Qt9VzKGilQ0LamE3c_urBMDSAIz7fzPGNoTr7ahJCz21XbUurorYn4S2nbPF_VtmDua06LaO9I_cMIVx7tlJVutAF3G4-RmlPvPHYUCRQWSFh31SciV-Y3HFVRsyUvwKzw4ktyk1Rbx0V6cWXM0ATsDUcAZ6K_IsfS-Z2DuNAsiBbIIQkn_dfwdPP9PvnKT4QX_8ALBkhzHGiW59Ciu5SFyHCxhs.y-eeQFB1C0cjdBMzQpLN4GfM6AKNbcvxvyFCeX0f-JU&dib_tag=se&keywords=1%27%27+universal+wheel&qid=1784149775&sprefix=1%27%27+universal+wh%2Caps%2C380&sr=8-4] |
| Ultrasonic sensor (HC-SR04) | Measures distance to objects directly in front | $4 | [https://www.amazon.com/WWZMDiB-HC-SR04-Ultrasonic-Distance-Measuring/dp/B0B1MJJLJP/ref=sr_1_3?crid=1XU51UGEJZZA&dib=eyJ2IjoiMSJ9.w-v74CMMP9eRh1BFF5BJ6xZlNH9LlX5HLX1Axp43FWYbpT_9h64LVT_hJcnFuLLU36s_1nGWoajK4N7MDmpkDbi2FD493Elxaym8UiH6arIe__PyXoq2LX7aqWpugzEO_DIOOE9O7vX_HJ8QIcJM-abGJFBGgxymELZqei_ECXRUWStpf-xokFMdnW2nMLgXaezf5zO9rvQcVLcFnicIB3Dl1lj33dbwYedAZPhl-Ik.3z9_LFUevjzpp-SKwPtmU7DxTibRFMN71Wcl6_aEQcs&dib_tag=se&keywords=ultrasonic%2Bsensor&qid=1784149948&sprefix=ultrasonic%2Bsensor%2Caps%2C172&sr=8-3&th=1] |
| IR obstacle avoidance sensors (2) | blind-spot detection | $2 | [https://www.amazon.com/Infrared-Avoidance-Transmitting-Receiving-Photoelectric/dp/B07PFCC76N/ref=sr_1_1_sspa?crid=1W5YFEYDI0TAN&dib=eyJ2IjoiMSJ9.AJ7Iwf87FduxzumjewKRxOmAi5Xj-dzRvvie66VtEjUUjJebZH84qJULVAep8bvjWIcJR2oe-9FJR8ISCxhgWZQwpoty4VFxdP3tR9nRl8F3o3cMreO_A9XCIcMVBg_JRK5hOp7hCcDnv139IADr-5_BOPE4Uq3DqQnUx7HJNTwxifXDAjcI7ucF9hpBmg4e47m7CsnKqfHjZ-1YEvrtV013Dl0Pj6NCSRrbcn3oa3M.6WuBqFHwK1_k9f3orEyMkvqrGOmmh38hm4BqnVZGnF0&dib_tag=se&keywords=ir%2Bobstacle%2Bavoidance%2Bsensor&qid=1784150037&sprefix=IR%2Bobstacle%2B%2Caps%2C158&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1] |
| Line Tracking sensor | detects high-contrast lane lines | $3 | [https://www.amazon.com/DAOKAI-1-Channel-Detection-Adjustable-Sensitivity/dp/B0BGYCZ8HV/ref=sr_1_4?crid=H1B0FAN2K89E&dib=eyJ2IjoiMSJ9.1OTPBSu98Sl867yOWO1flCILllw-0QqZtvZp3D8si2Kz1WSgKb4_d-sLOyanwLVDw77BkIZvPUzpY1jlj4geTm_jHJPNcWkJOSKRjr4Qkm7qiG59ZVwwA80TGFBJ2b1LxC9eyqRMslE05dL6EMA8QXS1Ic-b25xMAZa78AiXk0SQ8wGRYsgZybUFH4QKe67NbFriL1-fC9OcKObXPRRMAJE3SpExC9x_05BijchnwMc.sTi-PGZp0xF-08jSzn9W3Pa-0YpPqzdjWFZPFsJV608&dib_tag=se&keywords=line+tracking+sensor&qid=1784150157&sprefix=line+tracking+sensor%2Caps%2C221&sr=8-4] |
| RGB LEDs | Headlights communicating car's thinking | $1 | [https://www.amazon.com/Tricolor-Multicolor-Lighting-Electronics-Components/dp/B01C19ENFK/ref=sr_1_1_sspa?crid=1UH5PDO416YCP&dib=eyJ2IjoiMSJ9.BU4S0jVgvYFMaG3YX-8kv5g7mf-L7uSxfBvlcMa27TJ1IcyxNEUDHRcL-zCrf9taKn7gLzVMNdvy_gL4fTwFJKmGSUBJgakKHw3QBUgEA_rVF39r54SIFdE1wm14koM_xk0P2ebif6AHtdLXjbnXZLYJLDm41J-7Ras9nPEgaT76JTi2zYJQdkjuF0TbxoiPpMVQyw1-t38F1TzubAEUF8ZNE3OLj_eFGzmAovrfuaw.32ZuAA9otDqRrSfna6Yk4gSJv7bQJfL_sq-7c_leNXQ&dib_tag=se&keywords=RGB%2BLEDs&qid=1784150277&sprefix=rgb%2Bleds%2Caps%2C170&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1] |
| Mini breadboard | Distributes power to sensors and modules | $4 | [https://www.amazon.com/WWZMDiB-SYB-170-Breadboard-Plates-Multicolored/dp/B09YXQJMTG/ref=sr_1_1_sspa?crid=3MIJBKTKZTM3S&dib=eyJ2IjoiMSJ9.EQvCK09g_r0CejNbKABqFd6BZTf9pk6ztW2A000LkgvEt1uWVaC2byg0yHEhZqN-wzEYuDcVUCub58HrMcW9ODMdBF6paEFM6UeWIYLGYMqaL1gUy5LFXQP_WY6Nij-cANoSDVJCkX8DshniMZrE9Pb8TZKApd5A_szF8LlrToq-ttrPjSTO9pZp2G-D1Mv-PLzqmasLp4fzrEZXF3XReMW417_J6BfRORaHT-l0B1k.9WdNUTzZ8T2nKgcnpl3wboRahooREl3aFexta-No4CE&dib_tag=se&keywords=mini+breadboard&qid=1784150336&sprefix=mini+breadboar%2Caps%2C169&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1] |
| Car chassis (Sunfounder Kit) | Main mounting platform | $8 |[https://www.amazon.com/SunFounder-Ultimate-Tutorials-Beginners-Enthusiasts/dp/B0CGJ235XN/ref=sr_1_2_sspa?crid=2X74H3K1NMXVA&keywords=car+chassis+from+sunfounder&qid=1784150435&sprefix=car+chassis+from+sunfounde%2Caps%2C139&sr=8-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9tdGY&psc=1]|
| 9V Battery and clip cable | Portable power source | $4 | [https://www.amazon.com/PKCELL-Alkaline-9V-Detector-Batteries/dp/B0DG4QRJKQ/ref=sr_1_3_sspa?crid=1JALRZDVI4DBH&dib=eyJ2IjoiMSJ9.UTIEEJxrXzAacW7rXzP5baUO2v4AozDKVKm1_F2qlZHQ9hVteUKkel2la7e8OJUgaikzHh0dHlxqJbmWwF4VZwtJwmZD0QQTlisQcO7F_0ae2tTcY7W0_7NWs1p9548IwNEybt0lYddqBe9wztucsnXaGewAnErwssdUTeBfFZTztlB0YP-Cf-LcQOZgsBZlSoEiU_gvvOWXL3pLg1zp-7XYtY-8AVi5YYcckODXgMWX6UuAcru0lH39HzFiNWx-t1RSKrQ76S3ogAPm1R9AoTC3gr68fsC_hVxN0Yxjq3c.ZJpFVctMqKGLrhFPOZKaAcEtlhqpZyZuqHRdK9TDGDg&dib_tag=se&keywords=9V+battery&qid=1784150561&sprefix=9v+battery+%2Caps%2C181&sr=8-3-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1] |
| Jumper wires | Physical electrical connections | $2 | [https://www.amazon.com/WWZMDiB-120Pcs-Multicolored-Breadboard-Jumper/dp/B0B2L66ZFM/ref=sr_1_1_sspa?crid=1X65CJJW2TMHZ&dib=eyJ2IjoiMSJ9.I3nSspk5onl8Jong0G-0EaUV8k3yvkfNxu9EofYJ660_GAukluqKFTDs3FZ9XfRKGf2JDS-z84NqDSzLJ-WDAORU4znBSUEQeeaFqHWUsrCKMwH6q3pCBe0rts-vP06Mx53JRw5NW485BUAZ8cw9vI9jP1ThUOfMIMZ4eqjNVDbUX6Yep-H49NldtvjWZVAC1LCxP-YzbV7rskmRBbaTRNeTvV9zw-QjPVzqoJPZQos.9ZzrhVo1c-tKddZRj9hYr2B53wN0nk_WwewtlmUXxxM&dib_tag=se&keywords=jump+wires&qid=1784150611&sprefix=jump+wire%2Caps%2C174&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1] |



# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)

To watch the BSE tutorial on how to create a portfolio, click here.
