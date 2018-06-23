# Gut Microbiota Mechanisms

[![DOI](https://zenodo.org/badge/129404481.svg)](https://zenodo.org/badge/latestdoi/129404481)

An interactive model of gut microbiota mechanisms for restoring health. From Orr, M., Kocurek, K., and Young, D. 2018. Gut microbiota and human health: Insights from ecological restoration. _The Quarterly Review of Biology_ 93(2) pp 73-90.

## Development

To get a development environment up and running:

1. Fork and clone the repo
2. Edit _index.html_, making commits to the _master_ branch.
3. Merge _master_ into the _gh-pages_ branch for publication via GitHub pages.

## Mechanisms & Mathematics

The mechanisms are described by the fecal microbial transplant (FMT) success rate in a depleted donor, relative to the FMT success rate in an intact donor. This is described as:

**P<sub>D</sub> / P<sub>I</sub>**

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

**P<sub>I</sub>** is calculated using the binomial expansion equation:

**[ ( y! / (m! * (y - m)!) ) x<sup>m</sup> * q<sup>(y - m)</sup>]<sup>z</sup>**

Where:

  + **y = number of species/function in an intact donor**
  + **d = donor depletion**
  + **m = minimum number of species required to restore function**
  + **x = probability of each species establishing in recipient**
  + **q = 1 - x**
  + **z = number of functions needed to be restored**

### Note

Because of 64-bit limitations with JavaScript's maximum integer size, the equations cannot be used to safely compute all values for the visualization when the number of functions needed to be restored (z) is greater than 5. To distinguish `NaN` values from exceedingly large numbers, the computation uses `z = 5` when `z > 5`, as the numbers get set to 1 (100%) anyways when the result > 1. To distinguish `NaN` values from exceedingly small numbers, the computation rounds them down to 0.

## Deployment

To deploy:

1. Push your local _gh-pages_ branch to the remote _gh-pages_ branch.
2. (Optional) Submit a pull request.

---

(c) 2018 Ryder McDowell. All rights reserved.
