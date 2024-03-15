> Modulation is the process of converting data to electromagnetic waveforms. Conversely, **demodulation** is the process of converting EM waveforms to digital or analog data.

We note that a sinusoid modelling a waveform is characterised by: $$s(t)=a\cdot\cos\left(2\pi ft+\varphi\right)$$
for amplitude $a$, frequency $f$, time $t$ and phase $\varphi$.

## Analog Modulation
There are two basic modulation methods for analog signals. We consider the signal itself, in this case, this is a simple sine wave:
![[Screenshot 2023-10-05 at 11.33.40.png]]
The signal will have a carrier, which acts as the waveform being modulated according to the characteristics of the signal:
![[Screenshot 2023-10-05 at 11.35.18.png]]
### Amplitude Modulation
In **AM**, the carrier's amplitude is modulated according to the signal data. Using the above examples:
![[Screenshot 2023-10-05 at 11.36.49.png]]
More specifically, we define a signal, $s$ and carrier, $c$ as:
$$s = V_s \sin(\omega_s t)$$
$$c = V_c \sin(\omega_c t)$$
respectively, when considering the angular frequency $\omega = 2\pi f$.

Hence, we can calculate the value of the modulation, $V_{am}$ as:
$$V_{am} = (V_c + V_s \sin(\omega_s t)) \cdot \sin(\omega_c t)$$

### Frequency Modulation
In basic terms, **FM** is similar to AM, but is characterised by changes in frequency. Using the example above, this would be demonstrated as:
![[Screenshot 2023-10-05 at 11.52.24.png]]

## Digital Modulation
We will consider four types of modulation techniques.
### Basic Modulation Techniques
There are three basic techniques:
- Amplitude Shift Keying (ASK)
- Frequency Shift Keying (FSK)
- Phase Shift Keying (PSK)
These are characterised in the example below:
![[Screenshot 2023-10-05 at 11.55.36.png]]

### Quadrature Phase Shift Keying (QPSK)
**QPSK** is similar to PSK, but we consider four phase definition points (or angles). As such, we can convey two bits of information, rather than one.
![[Screenshot 2023-10-05 at 12.22.59.png]]

