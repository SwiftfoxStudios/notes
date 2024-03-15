These are a group of techniques used to widen signal bandwidth and reduce interference across multiple frequency channels.

There are two main methods:

## Direct Sequence (DSSS)
DSSS transmissions multiply the transmitted sequence with an added **chipping sequence** using an XOR operation. **Barker codes** are commonly used as chipping sequences and are often used in transmission delay detection.![[Screenshot 2023-10-10 at 19.43.32.png]]

The aim is that Barker codes, when multiplied with themselves (meaning a correct transmission), should result in the length of the transmission.

## Frequency Hopping (FHSS)
This reduces interference (and increases bandwidth) by changing the channel (and consequently, the frequency) of transmission at regular, pseudorandom intervals. By changing frequency regularly, interference across a singular channel does not affect the message when transmitting across other channels.

The hopping sequence is shared between the transmitter and the receiver. Bluetooth uses this method.