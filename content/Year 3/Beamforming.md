**Beamforming** is a signal processing technique for directional signal transmission.

Specifically, we can organise an antenna array that can send and receive signals, adding artificial delays to the signals depending on the distance between antennas such that the wavelengths from signals of particular angles act constructively, whilst others act destructively.

## Use Case Scenarios:
### Increasing Transmission Security
Imagine a set of two antennas, $a_1,a_2$ at a ground station with distance $d$ between them. If they each transmit a signal at some time epoch $t_1,t_2$ respectively, such that their wavelengths act constructively at a given angle and destructively at other angles (where an adversary may be located), information security can be preserved. 

### Noise Reduction
If we have several signal emitters but we know the location of a transmitter of interest, we can pick time delays to ensure the signals emitted by the transmitter of interest act constructively, increasing the *'beam'* strength.