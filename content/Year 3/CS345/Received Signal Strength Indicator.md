> RSSI is a measure of the power present in a received radio signal.

Generally, this strength model follows the inverse square law:
$$RSSI \propto \frac{1}{d^2}$$
In reality, external factors can affect this - such as [[Sensor Node#Diffraction|diffraction]] and [[Sensor Node#Scattering|scattering]], which affects path loss.

As such, the following formula is used. This is log-based due to $dBm$ power conversions, as decibels are logarithmic:
$$RSSI = -10n \log_{10}(d) - A$$
We can also use a *data-driven approach*, in which experimental results are used for curve fitting (*See Lab 2*):
![[Screenshot 2023-11-08 at 18.02.14.png|300]]



