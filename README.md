# R-2R Ladder Digital-to-Analog Converter

Research and hardware implementation exploring the R-2R resistor ladder digital-to-analog converter.

## Overview

The R-2R ladder is a digital-to-analog converter (DAC) architecture that converts a binary input into a corresponding analog output using only two resistor values: R and 2R.

I began this project while conducting independent research under Professor Aziz Inan at the University of Portland. My research focused on the historical development of the R-2R ladder and how its simple architecture addressed limitations of earlier DAC designs.

This work resulted in a first-author research manuscript titled *The Role of Simplicity in the Historical Development of the R-2R DAC Ladder Network*.

## Why R-2R?

Earlier binary-weighted DACs require resistor values that scale with each additional bit:

`R, 2R, 4R, 8R, 16R, ...`

As resolution increases, this creates increasingly large resistor ratios and makes precise implementation more difficult.

The R-2R ladder instead uses only two resistor values:

- R
- 2R

Additional bits can therefore be incorporated by extending the ladder while retaining the same two resistor values.

## Example: 3-Bit DAC

For a 3-bit R-2R DAC with a 5 V reference:

`Vout = Vref(B2/2 + B1/4 + B0/8)`

For the binary input `001`:

`Vout = 5(0/2 + 0/4 + 1/8) = 0.625 V`

Each successive bit contributes half the weight of the previous bit.

## Research Paper

**The Role of Simplicity in the Historical Development of the R-2R DAC Ladder Network**

Nathan Kim and Aziz Inan

The paper traces the development of the R-2R DAC architecture and examines how its simplicity addressed limitations of earlier digital-to-analog converter designs.

## Hardware Implementation

As part of the project, I constructed and tested an R-2R DAC using discrete resistors on a breadboard.

The circuit was tested using different binary input combinations, and the resulting analog output voltage was measured using a voltmeter. This provided a hands-on demonstration of the relationship between the digital input and analog output predicted by the R-2R architecture.

For example, for a 3-bit R-2R DAC using a 5 V reference, the binary input `001` has a theoretical output of:

`Vout = 5(1/8) = 0.625 V`

The original experimental data and photographs from the project were not retained, so this repository documents the circuit design, analysis, and research rather than reproducing the original measurements.
