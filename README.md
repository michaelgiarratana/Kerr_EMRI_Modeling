# Kerr EMRI Modeling

## Overview

This repository contains Mathematica notebooks for modeling extreme-mass-ratio inspirals (EMRIs) in Kerr spacetime and exploring their gravitational-wave signals through orbital animation and sonification.

Both notebooks begin by modeling the motion of a test particle orbiting a spinning black hole. They incorporate gravitational-wave radiation reaction to evolve the orbit over time and compute the separatrix, which marks the boundary between stable bound orbits and plunge trajectories.

The notebooks build on this shared orbital model to produce two different outputs:

- **Orbital animation**: Visualizes the time-dependent evolution of an eccentric, inclined orbit around a Kerr black hole.
- **Gravitational-wave sonification**: Calculates approximate gravitational-wave polarizations from the evolving orbit and converts the resulting signal into audible sound.

---

## Physical Model

The system uses the test-particle approximation, in which a small secondary object moves in the gravitational field of a much more massive, spinning black hole. The orbital evolution is driven by gravitational-wave emission, which causes the orbital parameters to change over time.

The model tracks the evolution of orbital quantities, including:

- Orbital energy \(E(t)\)
- Axial angular momentum \(L_z(t)\)
- Carter constant \(Q(t)\)
- Derived orbital elements (e.g. semi-latus rectum \(p(t)\), eccentricity \(e(t)\), inclination \(i(t)\))

The evolution of these quantities determines the changing orbital trajectory and provides the input for the subsequent animation and gravitational-wave calculations.

**Governing equations:**  
[insert equation(s) and/or reference paper(s) used]

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

## Notebook 1: Orbital Animation


The animation notebook evolves the orbital trajectory and constructs a sequence of frames representing the orbit at successive times.

The animation workflow:

- Computes the time-dependent orbital trajectory using the shared Kerr EMRI model.
- Generates parametric plots of the orbit at successive points in the evolution.
- Stores the resulting plots as frames in an array.
- Uses the frames to construct an animation of the evolving orbit.

The resulting animation illustrates features such as orbital precession and radiation-reaction-driven evolution. The below example shows an eccentric, inclined test-particle orbit around a spinning black hole, using the example input above.

![Orbital evolution animation](examples/KerrEccNoAxes.gif)

---

## Notebook 2: Gravitational-Wave Sonification

The sonification notebook uses the same orbital evolution framework to calculate an approximate gravitational-wave signal and convert it into audio.

**Gravitational Wave Calculation**

After establishing the orbital evolution, the notebook calculates quantities associated with the emitted gravitational radiation. Numerical derivatives of the orbital motion are used to construct time-dependent source multipole moments, including the mass quadrupole.

The time-dependent quadrupole information is then used to calculate the gravitational-wave polarizations in the relevant angular directions. The resulting, (h_+) and (h_\times), describe the two independent polarization states of the gravitational-wave signal.

The calculation produces a time series of values associated with the evolving orbit.

**Sonification**

To make the simulated signal audible, the notebook associates the calculated strain samples with their corresponding time values and passes the time-series data to Mathematica's `ListPlay`.

The playback sampling is scaled according to the mass of the binary system, allowing the simulated gravitational-wave signal to be represented as audio.

---

## Numerical Methods

The orbital evolution is computed using Mathematica's `NDSolve` framework with numerical integration. Numerical differentiation is also used in the gravitational-wave calculation.

- **NOTE**: Currently, the solver does not contain a stopping condition to halt the integration. The user must run the KerrRad function and abort the evaluation to stop the integration and obtain the evolving equations. This is a topic for a future modification. 

---

## Requirements

- Wolfram Mathematica and its `NumericalCalculus` package

---

## Repository Structure

- **Notebooks**: Mathematica notebooks for orbital animation and gravitational-wave sonification.
- **Examples**: Example animations, audio files, and other generated outputs.

---

## Contact

Correspondence:
giarratanamd@gmail.com
