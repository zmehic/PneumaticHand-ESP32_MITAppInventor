# PneumaticHand-ESP32_MITAppInventor
An application made in MIT App Inventor used to manage an ESP32 controlled glove with pneumatic tubing used for finger movement to assist patients recovering from a stroke. The project was supported by the Faculty od Information Technologies (FIT Mostar) and the Faculty of Mechanical Engineering (MF Mostar). Collegues from the MF worked on the physical glove, while my collegue [Armin Đidelija](https://github.com/ArminDjidelija) and I worked on the ESP32 and App part.

## Why MIT App Inventor?
At the time of making this application, the goal was to have the app connected to the ESP32 via Bluetooth LE. I've tried to establish the connection while making the app in .NET MAUI, and later on Flutter. Since I was unable to establish the connection (I wasn't very experiences at the time), I looked for other options. After some time, I've found an interesting [YouTube video](https://www.youtube.com/watch?v=aM2ktMKAunw&t=12s) showing the established connection between an ESP32 and an app made in MIT App Inventor used for turning the diodes on and off. After Armin and I figured out how everything works together, we split the work where Armin worked on the EPS32 code and I was responsible for the app part, while helping eachother in buggy situations on both parts. 

## How does it work?
### Connection to ESP32
<img src="https://github.com/zmehic/PneumaticHand-ESP32_MITAppInventor/assets/60481114/bf60fd15-f4a1-4100-abd0-7da7ab0bbef9" width="650" height="400">
<img src="https://github.com/zmehic/PneumaticHand-ESP32_MITAppInventor/assets/60481114/9fda23fd-805e-44cf-b586-32c4c6f64954" width="200" height="400">
<br>
<br>
By chosing the right controller (ESP32) from the list of devices found by the scan, you will be given all of the commands available to a user.

### Controls
<p align="left">

<img src="https://github.com/zmehic/PneumaticHand-ESP32_MITAppInventor/assets/60481114/274bf80b-0355-49e0-b953-972a9bc60f19" width="300" height="600">

</p>
<br>
<br>
If the user disconnects, the controls become invisible again.

#### Elements 1 & 2
Pressure value data is <b>recieved</b> from the ESP32(it uses a pressure sensor reading to get the value of gloves pressure). In element 1 the value is just represented as a label, while in element 2 it is presented on a graph showing the change in pressure values in time.

#### Element 3
Textarea that expects a patient name. It is crucial for tracking data collected from the ESP32.

#### Elements 4 & 6
Cycles, Repetitions and Pause are used to set the number of times a patients hand will open and close, with certain pauses between the opening/closing.
<br>
<br>
For example, let's say a patient sets the number of cycles to 3, repetitions to 5 and pause to 3. The hand will close and open 5 times with a pause between each repetition of 3 seconds before making a longer pause (pause * 2) of 6 seconds and entering the second of three cycles.

#### Element 6
This element is used to set the maximum pressure in the glove. Patient can alter this value to have his hand open more or less.

### Data storage
