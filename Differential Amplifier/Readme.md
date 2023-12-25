Differential Amplifier (5-Transistor Operational Transconductance Amplifier) <a name="TOP"></a>
===================

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/4e92f4c3-b7f3-42e7-9c41-bc294638cb50)

## Table of Contents
* [Theory](#Theory)
* [Simulation Procedure](#Simulation-Procedure)
* [Outputs](#Outputs)
* [References](#References)

## Theory
### What is a differential amplifier?

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/ccddb144-d8d7-45d4-a855-ba7dbc6a099a)

A MOSFET differential amplifier is a type of electronic amplifier that uses Metal-Oxide-Semiconductor Field-Effect Transistors (MOSFETs) as the active devices in its differential pair. The differential amplifier is a fundamental building block in analog circuit design and is commonly used in operational amplifiers, analog integrated circuits, and other applications.

### Why is a differential amplifier used?

* Differential amplifiers apply gain not to one input signal but to the difference between two input signals. This means that a differential amplifier naturally eliminates noise or interference that is present in both input signals.
* Differential amplification also suppresses common-mode signals—in other words, a DC offset that is present in both input signals will be removed, and the gain will be applied only to the signal of interest (assuming, of course, that the signal of interest is not present in both inputs). This is particularly advantageous in the context of IC design because it eliminates the need for bulky DC-blocking capacitors.
* The subtraction that occurs in a differential pair makes it easy to incorporate the circuit into a negative-feedback amplifier, and if you’ve read the Negative Feedback series, you know that negative feedback is about the best thing that could ever happen to an amplifier circuit.

## Specifications for the Design
![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/4ddb0e2e-1cf4-4def-87f4-9e46a90494a6)

## Simulation Procedure
* Step 1: Open the Cadence Virtuoso Design tool.
* Step 2: Create a new library using the CIW window (File -> New -> Library). Attach this library to the gpdk045nm technology node, or any other technology node.
* Step 3: Create a new cell view using the library manager window (File -> New -> Cell View). 
* Step 4: Start placing the components from the built-in analoglib component library.
  Components in the schematic:
  
  *  NMOS [nmos2v] (gpdk045)
  *  PMOS [pmos2v] (gpdk045)
  *  Voltage source VDD [vdd] = 1.8V (analoglib)
  *  Voltage source Vin [vin] = 0.7V DC + 1mV 1KHz Sine Wave (analoglib)
  *  Current source Iref [Iref] = 10uA (analoglib)
  *  Ground [gnd] (analoglib)

 Create the schematic as per the following circuit diagram:
![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/2db1e5d5-75b4-4344-8c2b-04ec4228ba30)

* Step 5: Launch ADE L for simulation
* Step 6: Choose the analysis method, then select the DC analysis and check the “save DC operating points” option.
* Step 7: Choose the analysis method, then select the Transient analysis and set the time from 0s to 50us.
* Step 8: Choose the analysis method, then select the AC analysis and set the frequency from 1Hz to 10GHz.
* Step 9: Choose the analysis method, then select the Stability (stb) analysis and set the time from 1Hz to 10GHz.
* Step 10: Select the “outputs” menu and then the “To be plotted on schematic” option and select the net plots you want.
* Step 11: Check the simulation type and nets to be plotted in the ADE L and hit the netlist and run option (green play button). The simulation will start, and the simulation results will be printed.
* Step 12: To get a sweep for any of the DC simulations, set the sweep range of any parameter such as Vdd from 0 to 1.8V or temperature from -50C to 125C.

## Outputs
* DC Operating Point Simulation: 5-T OTA (Vout = 0.7V; VinDC = 1.2V, VinAC = 1KHz Sine wave w/2mVpp amplitude)
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/6b4d1f92-e04e-47bd-bf80-5630d3ff3a95)

  Resultant DC operating points of a 5T-OTA

* 5-T OTA Transient simulation [0-10ms] (VinDC = 700mV, VinAC = 1KHz Sine wave w/2mVpp amplitude): [Gain = 52.6]
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/27d9597f-c0c5-423f-84b5-42d1b7c5b158)

  Resultant waveforms for the Vin+, Vin- & Vout of a 5T-OTA

## References
 - [1] [https://www.tutorialspoint.com/basic_electronics/basic_electronics_mosfet.htm](https://www.elprocus.com/differential-amplifier-circuit-using-transistors/)https://www.elprocus.com/differential-amplifier-circuit-using-transistors/
 - [2] https://www.allaboutcircuits.com/technical-articles/the-basic-mosfet-differential-pair
 - [3] https://sites.bu.edu/engcourses/files/2016/08/mosfet-differential-amplifier.pdf
