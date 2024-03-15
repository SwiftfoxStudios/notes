> Localisation is the process of geolocating an item (or person) of interest, indoors. Recently, this has been done using wireless access points.

We can use [[Received Signal Strength Indicator|RSSI]] to do this, as noted below.
## RSSI Localisation
### Trilateration
> Trilateration is the process of finding a point in space, given three calculated distances

This is similar to triangulation, but instead of known bearings, we have known distances. These are calculated using the RSSI model; given $RSSI,n,A$, we can estimate $d$. Using the distance, $d$, between a user and three access points, we can use trilateration to locate the user.

This becomes more difficult in complex buildings where the signal strength does not fit the model perfectly.
### RADAR
This is similar to trilateration, but uses $k-NN$ given a set of $>k$ access points.
### Principal Component Analysis
> *Main Page: see [[Principal Component Analysis]]*

> PCA is used for dimension reduction based on the analysis of correlations amongst attributes in a dataset, using the [[Covariance|covariance]] of the dataset.

Localisation can occur given a large number of access points and large number of possible locations (discrete). We can use only the most 'relevant' components (access points) for localisation.

## CSI Localisation
> Channel State Information (CSI) is the information contained within transmission between two antenna arrays.

This characterises the signal model between access points, using **MIMO**. Considering the matrix that describes transmission between two antennae $T_x,R_x$, we use a 4 dimensional tensor to represent the time series across multiple paths in the complex domain:
$$H \in \mathbb{C}^{N \cdot M \cdot K \cdot T}$$
![[Screenshot 2023-11-10 at 17.49.34.png]]

We note that using CSI for localisation is more stable, as it reduces the effects of interference and multipath propagation from using [[Multiplexing|OFDM]].