# Heartrate Monitor Smartwatch - Electronics Club
Led the development of a heartrate monitor smartwatch based on the ATmega328P microcontroller with a group of 4. Utilized several sensors to send/recieve data via I2C communication protocol using C based Arduino IDE. Designed custom PCB while analyzing several datasheets to reduce device size and create a more ergonomic user experience. 

This project was seperated into two teams. The Team 1 specialized in hardware development and was responsible for component selection, power distribution, datasheet analysis and PCB design. Team 2 interfaced with the microcontroller and sensors in the Arduino IDE by utilizing libraries like PulseSensor Playground, Adafruit_SSD1306, and RTClib. While I primarily led Team 1, I also served as the mediator for cross-team communication to ensure hardware and software supported each other.

## Smartwatch Project Objectives

| Feature | Description | Goal |
| :--- | :--- | :--- |
| **Heart Rate Monitor** | Integrate Pulse Sensor | Provides accurate heartrate measurments. |
| **OLED Display** | OLED Display | Clear visual output for biometric data and time. |
| **Timekeeping** | RTC (Real-Time Clock) | Maintain precise time and date. |
| **Power System** | Rechargeable LiPo | Provides rechargeable power. |

Throughout every iteration of this project we may have moved forward with different components that better fit our needs, however, the 4 underlying features above were included in every version of this project. 

## Proof of Concept

<img src="images/ProofofConcept.JPG" width="500">


The image above shows the first prototype of our Smartwatch. This version was based off of Arduino's smallest dev board the Pro Mini which houses the ATmega328P as its microcontroller (we would later use on the final versions of our project). To provide the functionalities we desired, we ordered several Arduino compatible modules that we could power and hook up to specific digital pins on the Pro Micro. In the table below is the comprehensive parts list we used for our first prototype:

| Feature | Part Name | Image |
| :--- | :--- | :--- |
| **Microcontroller** | Arduino Pro Micro | <img src="images/arduinopromicro.jpg" width="200"> |
| **Heart Rate Monitor** | Integrate Pulse Sensor | <img src="images/pulsesensor.jpg" width="200">|
| **OLED Display** | OLED Display | <img src="images/oled.png" width="200"> |
| **Timekeeping** | RTC (Real-Time Clock) | <img src="images/DS3231.jpg" width="200">|
| **Power System** | Rechargeable LiPo |<img src="images/lipo.jpg" width="200"> |

To turn our bread board prototype into something that resembeled a watch, we soldered the modules together trying to keep wires as short as possible. The following video shows the result:


https://github.com/user-attachments/assets/febb02ad-0546-478b-9966-6aa6d14cd212

t

The OLED display shows time, date, and current heartrate reading. Team 2 was able to program the Pro Micro to read from the RTC module and pulse sensor then display the results on the OLED. The pulse sensor results fluctuated quite a bit. After some research, we attributed this to the quality of the sensor itself. Many cheap pulse sensors use a method called photoplethysmography (PPG) to measure the change in blood volume in your capillaries as you heart beats. The pulse sensor module uses a green LED to shine light into the capillaries and a photodetector to measure how much light is reflected back. Ideally, the pulse sensor can translate this information into an accurate heart rate reading. PPG is cheap, however, its very sensitive to real world motion, ambient light interference and sensor contact. 
[*references*](https://www.sciencedirect.com/topics/engineering/sensor-pulse#:~:text=A%20pulse%20sensor%20is%20defined,Arduino%20for%20health%20monitoring%20applications.)

More accurate pulse sensors (professional grade) cost hundreds or thousands of dollars. Luckily, there is a cheaper PPG option, the MAX30102, that uses multi-wavelngth LEDs and has an on board processing IC. It also includes Sp02 readings as an added feature. We later decided to switch to the MAX30102 pulse oximeter to replace the pulse sensor module.




