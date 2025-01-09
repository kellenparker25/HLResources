# Ultrasonic Distance Sensor + OLED Display
|<img src="https://github.com/CCAHybridLab/HLResources/assets/63166855/fdc98498-3b51-4776-a57e-e7fd0a68bac4" width="400"/>|<img src="https://github.com/CCAHybridLab/HLResources/blob/main/Tutorials/Arduino/Ultrasonic-distance%2BOLED-Display/wiring-ultrasonic-distance%2BOLED-display.png" width="600"/>|
|--|--|

## Equipment
Don't have the parts? Build and test digitally on [Tinkercad](https://www.tinkercad.com/things/cYTtEqcJcwH-amazing-fulffy/editel?tenant=circuits)
- [Arduino Uno](https://airtable.com/appCpmcjYA1vwj8jn/tblOHGyZIGOZuJhCj/viwcQ6Lj5fpoG6Hvh/recQ1P43HKyVMjA79?blocks=hide)
- [HC-SR04 Ultrasonic distance sensor](https://airtable.com/appCpmcjYA1vwj8jn/tblZBoJcxkwHEMrXX/viwnKOWwUT76Q9RQV/recMg76eFUkjVesqo?blocks=hide)
- [SSD1306 0.96 inch I2C OLED](https://airtable.com/appCpmcjYA1vwj8jn/tblZz5NUA546g9J6o/viwu3SMJU1AEGhMGK/recW9AWeKOTIZbg60?blocks=hide)
- [Breadboard](https://airtable.com/appCpmcjYA1vwj8jn/tblZz5NUA546g9J6o/viwu3SMJU1AEGhMGK/recF514LASWf2n9LH?blocks=hide)
## Step 1: Ultrasonic Distance Sensor
- Follow [Mechatronics Guide](https://howtomechatronics.com/tutorials/arduino/ultrasonic-sensor-hc-sr04/)
- Watch [Mechatronics Video Tutorial (included in above tutorial)](https://www.youtube.com/watch?v=ZejQOX69K5M&t=20s) <br/>
*note: the video uses pin 9 and 10 for trig and echo respectively. Our demo uses pin 6 and 5 for trig and echo respectively.*
#### Move on to Step 2 once you're seeing accurate distance data on serial monitor
## Step 2: OLED Display
- Follow [this guide](https://randomnerdtutorials.com/guide-for-oled-display-with-arduino/) <br/>
  *note: complete through the "“Hello, world!” OLED Display"*
#### Move on to Step 3 once you see "Hello, world!" printed on display
## Step 3: Put them together!
```C++
#include <Wire.h>
#include <Adafruit_GFX.h>
#include <Adafruit_SSD1306.h>

#define SCREEN_WIDTH 128 // OLED display width, in pixels
#define SCREEN_HEIGHT 64 // OLED display height, in pixels

// Distance Sensor
const int trigPin = 6;
const int echoPin = 5;
long duration;
int distanceInch;
int distanceCm;

// Declaration for an SSD1306 display connected to I2C (SDA, SCL pins)
Adafruit_SSD1306 display(SCREEN_WIDTH, SCREEN_HEIGHT, &Wire, -1);

void setup() {
  Serial.begin(9600);

  // Distance sensor setup
  pinMode(trigPin, OUTPUT);
	pinMode(echoPin, INPUT);

  // OLED setup
  if(!display.begin(SSD1306_SWITCHCAPVCC, 0x3C)) { // Address 0x3D for 128x64
    Serial.println(F("SSD1306 allocation failed"));
    for(;;);
  }
  delay(2000);
  display.clearDisplay();
}

void loop() {
  // Distance Sensor Data
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  duration = pulseIn(echoPin, HIGH);
  distanceInch = duration * 0.0133 / 2;
  distanceCm = duration * 0.034 / 2;

  // Print distance to display
  display.clearDisplay();

  display.setTextSize(2);
  display.setTextColor(WHITE);
  display.setCursor(0, 0); // start of yellow section
  display.println("Distance:");

  display.setTextSize(3);
  display.setCursor(0, 16); // start of blue section
  display.print(distanceCm);
  display.print(" cm");
  delay(10);
  display.setCursor(0, 40);
  display.print(distanceInch);
  display.print(" inch");
  delay(10);

  display.display();
}
```
