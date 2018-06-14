# Gut Microbiota Mechanisms

An interactive model of gut microbiota mechanisms for restoring health. From Orr, M., Kocurek, K., and Young, D. 2018. Gut microbiota and human health: Insights from ecological restoration. _The Quarterly Review of Biology_ 93(2) pp 73-90.

## Development

To get a development environment up and running:
1. Fork the repo
2. Clone
3. Switch to branch: gh-pages
4. Code!

---

## Mechanisms/Mathematics

The mechanisms are described by the FMT success rate in a depleted donor relative to the FMT success rate in an intact donor. This is described as:

**P<sub>D</sub> / P<sub>I</sub>**

<br />
**P<sub>D</sub>** is calculated using the binomial expansion equation:

**[ ( yd! / (m! * (yd - m)!) ) x<sup>m</sup> * q<sup>(yd - m)</sup>]<sup>z</sup>**

Where:

  + **yd = (1 - d) * y**
  + **y = number of species/function in an intact donor**
  + **d = donor depletion**
  + **m = minimum number of species required to restore function**
  + **x = probability of each species establishing in recipient**
  + **q = 1 - x**
  + **z = number of functions needed to be restored**

<br />
**P<sub>I</sub>** is calculated using the binomial expansion equation:

**[ ( y! / (m! * (y - m)!) ) x<sup>m</sup> * q<sup>(y - m)</sup>]<sup>z</sup>**

Where:

  + **y = number of species/function in an intact donor**
  + **d = donor depletion**
  + **m = minimum number of species required to restore function**
  + **x = probability of each species establishing in recipient**
  + **q = 1 - x**
  + **z = number of functions needed to be restored**

<br />
Note: <br />
Because of 64-bit limitations with JavaScript's maximum integer size, the equations cannot be used to safely compute all values for the visualization when the number of functions needed to be restored (z) is greater than 5. To avoid NaN values from exceedingly large numbers, the computation uses z = 5 when z > 5, as the numbers get set to 1 (100%) anyways when the result > 1. To avoid NaN values from exceedingly small numbers, the computation rounds them to 0.

---

## Deployment

To deploy:
1. Push to branch gh-pages
2. Submit a pull request

---
(c) 2018 Ryder McDowell. All rights reserved.
