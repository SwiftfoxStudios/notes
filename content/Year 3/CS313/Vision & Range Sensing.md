> **Range** sensors are used to detect the distance between the sensing body and an observed body.
> **Vision** sensors are used to map the local environment.

## Time of Flight Ranging
> ToFR uses wave propagation to measure the time of flight of an object in a medium.

The quality of measurement is dependent on:
- Specular reflections
- Noise
- Doppler shift
- Transmission angle

## Phase Shift Measurement
> PSM utilises a beam splitter to calculate distance. In practice, this requires complex setup.

![[Screenshot 2024-01-16 at 14.28.23.png]]
It also does not always produce correct results, as the phase shift is 0 at all distances $D + n\lambda$.

## Triangulation
> Given a sensor with two known points, each with an angle incident to a third point, the distance to the third point can be calculated using the *sine rule*.

![[Screenshot 2024-01-16 at 14.33.27.png|300]]

In the above example, we determine $l_2$ using the known values $\alpha, \Theta, l_1$:
$$\frac{l_1}{\sin(180-\alpha-\Theta)}=\frac{l_2}{sin(\alpha)}$$

$$\frac{l_1 \cdot \sin(\alpha)}{\sin(180-\alpha-\Theta)}=l_2$$
## Sonar & Radar
> Sonar utilises sound waves to determine distance.
> Radar does the same with radio waves (which travel at $c$).

Sonar has a limited range and bandwidth but is conceptually simple.
Radar has a longer range but requires [[Beamforming]].
## LiDAR
> LiDAR uses light waves to determine distance. This is expensive and power hungry but extremely fast and accurate.

## Beacons
> Robot localisation can be performed by [[Indoor Localisation#Trilateration|trilateration]], nominally ([[GPS]]), via the use of beacons.

This is less effective indoors due to signal reflection. Dynamic environments often influence their success too.