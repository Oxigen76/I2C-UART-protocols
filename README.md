# I2C-UART-protocols
I2C and UART are two communication protocols utilised in microcontrollers and electronic devices to facilitate data exchange between them. This part of the assignment intends to explicate each protocol and furnish exemplary programming codes for Arduino.

The Universal Asynchronous Receiver/Transmitter (UART) is a serial communication protocol that employs a pair of wires, namely Transmit (TX) and Receive (RX). Asynchronous communication is characterised by the absence of a clock signal to synchronise data transfer.

In the context of UART communication, it is customary for each device to be equipped with a transmit (TX) pin and a receive (RX) pin. Therefore, to facilitate communication, it is necessary to connect the transmitting device's TX pin to the receiving device's RX pin and vice versa.

Information is conveyed through packets that consist of start bits, data bits, and stop bits. Parity bits may also be included to detect errors, although this is not mandatory.




