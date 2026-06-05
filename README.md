# Test Particle Orbital Evolution in Kerr Spacetime (Mathematica Notebook)

## Overview

This repository contains a Mathematica notebook that models the evolution of test-particle orbits around a spinning (Kerr) black hole under the influence of gravitational-wave emission.

The framework evolves orbital parameters in time using radiation-reaction-driven equations of motion, tracking the secular evolution of key conserved quantities and orbital elements.

---

## Physical Model

The system is based on a test-particle approximation in Kerr spacetime, where the secondary object evolves under dissipative effects due to gravitational radiation.

The evolution includes:

- Orbital energy \(E(t)\)
- Axial angular momentum \(L_z(t)\)
- Carter constant \(Q(t)\)
- Derived orbital elements (e.g. semi-latus rectum \(p(t)\), eccentricity \(e(t)\), inclination \(i(t)\))

**Governing equations:**  
[PLACEHOLDER: insert equation(s) scheme / reference paper(s) used]

---

## Inputs

The main function accepts initial binary parameters, including:

- Black hole spin \(a/M\)
- Initial semi-latus rectum \(p_0\)
- Initial eccentricity \(e_0\)
- Inclination angle between orbital plane and BH spin axis
- Initial orbital phases (if applicable)
- Black hole mass parameters

Example: KerrRad[a = 0.9, p = 40, e = 0.9, 
 i = 45, $\nu$ = 1, $\Theta$ = $\pi$, $\Phi$ = 0, M = 5]

---

## Outputs

The code evolves the system forward in time and returns:

- Time series evolution of orbital constants
- Derived orbital parameters as functions of time

---

## Visualization

The notebook includes an animation module that:

- Constructs a time series of orbital trajectories
- Generates a visual animation of the inspiral evolution
- Illustrates orbital precession and radiation-driven decay


---

## Numerical Methods

The evolution is performed using Mathematica’s `NDSolve` framework with adaptive integration.

- **NOTE**: Currently, the solver does not contain a stopping condition to halt the integration. The user must run the KerrRad function and abort the evaluation to stop the integration and obtain the evolving equations. This is a topic for a future modification. 

---

## Requirements

- Wolfram Mathematica (version: 13.1)
- Packages like `NumericalCalculus`` are imported to compute the GW polarizations. These functions will also be made available soon.

---

## Contact

Correspondence:
giarratanamd@gmail.com
