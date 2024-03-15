> Signature matching is the method used for a [[robot]] to remember a place it has already visited, based on signatures determined during [[Robot Localisation]].

We can use a correlation test, such as [[Mean Squared Error|MSE]], to match the signature of two places (specifically, a histogram representing the sensor readings (distance vs angle) at two distinct timesteps).

The orientation of the robot can also be matched - this is represented by a circular shift in the histogram values.