# I2C-UART-protocols
I2C and UART are two communication protocols utilised in microcontrollers and electronic devices to facilitate data exchange between them. This part of the assignment intends to explicate each protocol and furnish exemplary programming codes for Arduino.

The Universal Asynchronous Receiver/Transmitter (UART) is a serial communication protocol that employs a pair of wires, namely Transmit (TX) and Receive (RX). Asynchronous communication is characterised by the absence of a clock signal to synchronise data transfer.

In the context of UART communication, it is customary for each device to be equipped with a transmit (TX) pin and a receive (RX) pin. Therefore, to facilitate communication, it is necessary to connect the transmitting device's TX pin to the receiving device's RX pin and vice versa.

Information is conveyed through packets that consist of start bits, data bits, and stop bits. Parity bits may also be included to detect errors, although this is not mandatory.
Here's an example of UART communication between two Arduino boards:
![image](https://github.com/Oxigen76/I2C-UART-protocols/assets/76484497/912a54f8-044e-4f69-90ab-19f5ddb47e56)

![image](https://github.com/Oxigen76/I2C-UART-protocols/assets/76484497/122dbb67-7b15-48e6-a270-8515a593b2a9)

![image](https://github.com/Oxigen76/I2C-UART-protocols/assets/76484497/8c108f61-fc41-498f-a686-b6cf01a45773)

![image](https://github.com/Oxigen76/I2C-UART-protocols/assets/76484497/cbe0f751-c86b-461e-b555-80e1f2a3ec64)

Project details on:
https://www.tinkercad.com/things/0SYVH7ibyho?sharecode=VGLsjrFgx8dsUceHDcU_-MbmvVp1N7TFqOqT6o2of5k

The Inter-Integrated Circuit (I2C) is a communication protocol that employs a two-wire interface. It was initially developed by Philips, which is now known as NXP. The system utilises a master-slave architectural model that facilitates the connection of multiple devices on a single bus. The I2C communication protocol employs two distinct wires, the Serial Data Line (SDA) and the Serial Clock Line (SCL).

The acronym SDA is commonly employed to denote the data transfer process between various electronic devices.

The SCL signal serves as a means of synchronising data transfer by providing a clock signal.

The I2C communication protocol involves the master device generating the clock signal and initiating communication with the slave devices. Every individual slave device is assigned a different address, which the master utilises to establish contact with a particular slave.

Here is an example of I2C communication between two Arduino boards (Master and Slave):

![image](https://github.com/Oxigen76/I2C-UART-protocols/assets/76484497/6003de50-782c-4363-bba3-69412d289d3f)


![image](https://github.com/Oxigen76/I2C-UART-protocols/assets/76484497/5d1aa693-32ea-4ad0-9de8-b8ef1dcded20)


![image](https://github.com/Oxigen76/I2C-UART-protocols/assets/76484497/684758a1-a019-47f1-846c-ecb9b449c16d)


![image](https://github.com/Oxigen76/I2C-UART-protocols/assets/76484497/dbfea09b-e98b-4b29-8cd4-ee9f62837712)


Project details on:
https://www.tinkercad.com/things/4xyzTreuhsK?sharecode=K8drE-MWxtyw4O5W9lw4cTQUytDAVHl3fYUJv4_EDWg


