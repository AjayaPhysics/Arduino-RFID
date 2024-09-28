# Arduino-RFID
Arduino RFID with LCD display and LED
The module shown in the image is an I2C interface for an LCD display, commonly used to simplify connections to an Arduino and reduce the number of required pins. This type of module is usually used to control an LCD display (like a 16x2 or 20x4) in Arduino projects, such as your RFID and LED project.

Here’s a step-by-step breakdown of how you could integrate this component with an RFID module and LEDs in an Arduino project:

Project Overview: Arduino RFID with LED and LCD Display
The project involves using an RFID reader to scan tags, lighting up LEDs based on different tags, and displaying messages on the LCD.

Components You Will Need:
Arduino Uno (or compatible): To control the entire project.
RFID Module (RC522): To read RFID tags.
LEDs (3 different colors): To indicate different tag scans.
LCD Display (16x2 or 20x4): To display text based on the RFID tag scanned, interfaced using the I2C module (as seen in the image).
Jumper wires: For connections.
Breadboard: To organize connections.
Step 1: Wiring the Components
I2C LCD Display (as shown in the image):

VCC -> 5V on Arduino
GND -> GND on Arduino
SDA -> A4 on Arduino
SCL -> A5 on Arduino
RFID Module (RC522):

VCC -> 3.3V on Arduino
RST -> Digital pin 9
GND -> GND on Arduino
MISO -> Digital pin 12
MOSI -> Digital pin 11
SCK -> Digital pin 13
SS/SDA -> Digital pin 10
LEDs:

Connect the positive legs of the LEDs to digital pins on the Arduino (e.g., 2, 3, 4 for red, green, and blue).
Connect the negative legs to GND using resistors.
Step 2: Coding for Arduino
Libraries:

Install the following libraries in the Arduino IDE:
LiquidCrystal_I2C for the LCD
MFRC522 for the RFID reader
The potentiometer (blue square) on the I2C module is for adjusting the contrast of the LCD.
Make sure the I2C address (commonly 0x27) in the code matches the actual address of your module. You can scan for I2C devices using an I2C scanner sketch.
Modify the UID tags (12345678 and 87654321) in the code to match the actual tags you will be using in your project.
