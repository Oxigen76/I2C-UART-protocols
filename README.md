# I2C-UART-protocols

I2C and UART are two communication protocols utilised in microcontrollers and electronic devices to facilitate data exchange between them. This repository aims to provide an understanding of each protocol and offer exemplary programming codes for Arduino.

## Universal Asynchronous Receiver/Transmitter (UART)


UART is a serial communication protocol that employs a pair of wires, namely Transmit (TX) and Receive (RX). Asynchronous communication is characterised by the absence of a clock signal to synchronise data transfer. In the context of UART communication, each device has a transmit (TX) pin and a receive (RX) pin. To facilitate communication, connect the transmitting device's TX pin to the receiving device's RX pin and vice versa. Information is conveyed through packets that consist of start bits, data bits, and stop bits. Parity bits may also be included to detect errors, although this is not mandatory.

Here's an example of UART communication between two Arduino boards:

<p align="center">
    <img width="675" alt="Screenshot 2023-07-25 at 23 06 13" src="https://github.com/Oxigen76/I2C-UART-protocols/assets/76484497/da392e71-fd47-43a7-9423-1331d8d379b8">
    <br>
    <em>Figure 1: UART Components</em>
</p>


<p align="center">
    <img width="675" alt="Screenshot 2023-07-25 at 23 06 39" src="https://github.com/Oxigen76/I2C-UART-protocols/assets/76484497/338eb3ff-0a1e-40f7-a4e2-797dfba95abf">
    <br>
    <em>Figure 2: UART Schematic View</em>
</p>

<p align="center">
    <img width="1338" alt="Screenshot 2023-07-25 at 23 05 34" src="https://github.com/Oxigen76/I2C-UART-protocols/assets/76484497/954d2e99-c16a-4d2d-8a41-2efc07f184cb">
    <br>
    <em>Figure 3: UART Example </em>
</p>

Here is an example code for a simple UART communication:

```cpp
const int ledPin = 13;

void setup() {
  pinMode(ledPin, OUTPUT);
  
  Serial.begin(9600); // Initialize the Serial communication at 9600 baud rate
}

void loop() {
  if (Serial.available() > 0) {
    String receivedMessage = Serial.readStringUntil('\n'); // Read the received string from the master
    receivedMessage.trim(); // Remove any leading or trailing white spaces, including newline characters
    
    if (receivedMessage == "Pressed") { // Button is pressed
      digitalWrite(ledPin, HIGH); // Turn on the LED
    } else if (receivedMessage == "Released") { // Button is released
      digitalWrite(ledPin, LOW); // Turn off the LED
    }
  }
}
``` 


Complete project details can be found on Tinkercad <a href="https://www.tinkercad.com/things/0SYVH7ibyho?sharecode=VGLsjrFgx8dsUceHDcU_-MbmvVp1N7TFqOqT6o2of5k" target="_blank">here</a>.





## Inter-Integrated Circuit (I2C)

I2C is a communication protocol that employs a two-wire interface. Initially developed by Philips (now known as NXP), the system utilises a master-slave architectural model that facilitates the connection of multiple devices on a single bus. The I2C communication protocol uses the Serial Data Line (SDA) and the Serial Clock Line (SCL). The SDA denotes the data transfer process between various electronic devices. The SCL signal synchronises data transfer by providing a clock signal. The I2C communication protocol involves the master device generating the clock signal and initiating communication with the slave devices. Each slave device is assigned a different address, which the master uses to establish contact with a particular slave.

Here's an example of I2C communication between two Arduino boards (Master and Slave):

<p align="center">
    <img width="673" alt="Screenshot 2023-07-26 at 06 52 44" src="https://github.com/Oxigen76/I2C-UART-protocols/assets/76484497/565b017e-207a-47f0-8443-62dca98e2595">
    <br>
    <em>Figure 4: I2C Components</em>
</p>

<p align="center">
    <img width="673" alt="Screenshot 2023-07-26 at 06 53 00" src="https://github.com/Oxigen76/I2C-UART-protocols/assets/76484497/13659f40-f29e-4ad1-a12f-d1ee3671829c">
    <br>
    <em>Figure 5: I2C Shematic View</em>
</p>

<p align="center">
    <img width="1237" alt="Screenshot 2023-07-26 at 06 52 15" src="https://github.com/Oxigen76/I2C-UART-protocols/assets/76484497/404a0d1a-3a01-4154-aaf0-3c69fa46a81b">
    <br>
    <em>Figure 6: I2C Example</em>
</p>

Here's an example of I2C communication between two Arduino boards:

```cpp

#include <Wire.h>

const int ledPin = 13;
int buttonState = 0;

void setup() {
  pinMode(ledPin, OUTPUT);
  Wire.begin(8); // Join the I2C bus as a slave with address 8
  Wire.onReceive(receiveEvent); // Attach an event to be called when data is received
}

void loop() {
  // The loop function is empty since the communication is handled by the receiveEvent function
}

void receiveEvent(int bytes) {
  buttonState = Wire.read(); // Read the button state from the master

  if (buttonState == LOW) { // Button press now reads LOW due to the pull-up resistor
    digitalWrite(ledPin, HIGH); // Turn on the LED
  } else {
    digitalWrite(ledPin, LOW); // Turn off the LED
  }
}
``` 

Complete project details can be found on Tinkercad [here](https://www.tinkercad.com/things/4xyzTreuhsK?sharecode=K8drE-MWxtyw4O5W9lw4cTQUytDAVHl3fYUJv4_EDWg).
