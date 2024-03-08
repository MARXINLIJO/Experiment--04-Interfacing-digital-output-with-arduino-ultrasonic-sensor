# EXPERIMENT-NO--04-Distance measurement using Ultrasonic sensor
## AIM: 
To interface an ultrasonic pair and measure the distance in centimeters , calculate the error
 
### COMPONENTS REQUIRED:
1.	ultrasonic sensor module HC-SR04
2.	1 KΩ resistor 
3.	Arduino Uno 
4.	USB Interfacing cable 
5.	Connecting wires 


### THEORY: 
The HC-SR04 ultrasonic sensor uses SONAR to determine the distance of an object just like the bats do. It offers excellent non-contact range detection with high accuracy and stable readings in an easy-to-use package from 2 cm to 400 cm or 1” to 13 feet.

The operation is not affected by sunlight or black material, although acoustically, soft materials like cloth can be difficult to detect. It comes complete with ultrasonic transmitter and receiver module.
Technical Specifications
Power Supply − +5V DC
Quiescent Current − <2mA
Working Current − 15mA
Effectual Angle − <15°
Ranging Distance − 2cm – 400 cm/1″ – 13ft
Resolution − 0.3 cm
Measuring Angle − 30 degree

The ultrasonic sensor uses sonar to determine the distance to an object. Here’s what happens:

The ultrasound transmitter (trig pin) emits a high-frequency sound (40 kHz).
The sound travels through the air. If it finds an object, it bounces back to the module.
The ultrasound receiver (echo pin) receives the reflected sound (echo).
The time between the transmission and reception of the signal allows us to calculate the distance to an object. This is possible because we know the sound’s velocity in the air. Here’s the formula:

distance to an object = ((speed of sound in the air)*time)/2
speed of sound in the air at 20ºC (68ºF) = 343m/s

### FIGURE 01 CIRCUIT OF INTERFACING ULTRASONIC SENSOR 


![image](https://user-images.githubusercontent.com/36288975/166430594-5adb4ca9-5a42-4781-a7e6-7236b3766a85.png)



### PROCEDURE:
1.	Connect the circuit as per the circuit diagram 
2.	Connect the board to your computer via the USB cable.
3.	If needed, install the drivers.
4.	Launch the Arduino IDE.
5.	Select the board (If you the board is arduino uno, select accordingly).
6.	Select your serial port, accordingly ( E.g. COM5 )
7.	Open the file of the program  and verify the error , clear if any errors that are existing 
8.	Upload the program and check for the physical working. 
9.	Ensure safety before powering up the device 
10.	Plot the graph for the output voltage vs the resistance 


### PROGRAM 
```
// C++ code
//
int echopin=6;
int trigpin=7;
int red=7;
int green=9;
long duration;
float distance;
void setup()
{
  pinMode(echopin,INPUT);
  pinMode(trigpin,OUTPUT);
  pinMode(red,OUTPUT);
  pinMode(green,OUTPUT);
  Serial.begin(9600);
}
void loop()
{
  digitalWrite(trigpin,LOW);
  delay(10);
  digitalWrite(trigpin, HIGH);
  delay(10);
  digitalWrite(trigpin, LOW);
  duration=pulseIn(echopin,HIGH);
  distance=duration*0.034/2;
  Serial.print("distance=");
  Serial.print(distance);
  Serial.println("cms");
  if(distance>50)
  {
    digitalWrite(red,HIGH);
    delay(500);
    digitalWrite(red,LOW);
    delay(500);
  }
   else
  {
     digitalWrite(green,HIGH);
    delay(500);
    digitalWrite(green,LOW);
    delay(500);
    
  }

}
```
## OUTPUT:
# GREEN:
![Screenshot 2024-03-08 110025](https://github.com/MARXINLIJO/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/145742540/8a956ec5-9e58-4442-b5d1-3a5da8e85a57)
# RED:
![Screenshot 2024-03-08 110025](https://github.com/MARXINLIJO/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/145742540/7efa947a-a867-4969-ac19-b81d8b8b59ee)

### DISTANCE VS MEASUREMENT TABLE:
![Screenshot 2024-03-08 104030](https://github.com/MARXINLIJO/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/145742540/6bd8767a-6309-48ad-b85e-5c1de4429a67)
## GRAPH:
![Screenshot 2024-03-08 114219](https://github.com/MARXINLIJO/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/145742540/9a9dc43d-81b4-4ec5-aeba-ce6482eacf60)

## SCHEMATIC VIEW:
![Screenshot 2024-03-08 105849](https://github.com/MARXINLIJO/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/145742540/b1e14e6c-dd68-4aa9-85df-8ea0a5a3fef7)

## RESULT:
Thus the distance value is measured in "CM" using ultrasonic sensor.
```
Average error = sum/ number of readings
=(0.09+0.16+0.31+0.41+0.42)/5
=0.278
```			




 
