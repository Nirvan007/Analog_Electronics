2-Stage Operational Amplifier (Opamp) <a name="TOP"></a>
===================

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/9b2a1fc2-092f-40ef-8230-c367e254c5af)

## Table of Contents
* [Theory](#Theory)
* [Specifications for the Design](#Specifications-for-the-Design)
* [Simulation Procedure](#Simulation-Procedure)
* [Outputs](#Outputs)
* [References](#References)

## Theory
### What is an operational amplifier?

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/edb40ea7-29e9-4894-8c2b-6a03709baa3e)

An operational amplifier (op amp) is an analog circuit block that takes a differential voltage input and produces a single-ended voltage output. Op amps usually have three terminals: two high-impedance inputs and a low-impedance output port. The inverting input is denoted with a minus (-) sign, and the non-inverting input uses a positive (+) sign. Operational amplifiers work to amplify the voltage differential between the inputs, which is useful for a variety of analog functions including signal chain, power, and control applications.

### Operational Amplifier Clasifications

There are four ways to classify operational amplifiers:
* Voltage amplifiers take voltage in and produce a voltage at the output.
* Current amplifiers receive a current input and produce a current output.
* Transconductance amplifiers convert a voltage input to a current output.
* Transresistance amplifiers convert a current input and produces a voltage output.

### Characteristics and Parameters of an Ideal Opamp

An ideal op amp is usually considered to have the following characteristics
* Infinite open-loop gain G = vout / vin
* Infinite input impedance Rin, and so zero input current
* Zero input offset voltage
* Infinite output voltage range
* Infinite bandwidth with zero phase shift and infinite slew rateZero output impedance Rout, and so infinite output current range
* Zero noise
* Infinite common-mode rejection ratio (CMRR)
* Infinite power supply rejection ratio

These ideals can be summarized by the two golden rules:
* In a closed loop the output does whatever is necessary to make the voltage difference between the inputs zero
* The inputs draw zero current

### Frequency response and bandwidth (BW)
An ideal op amp would have an infinite bandwidth (BW), and would be able to maintain a high gain regardless of signal frequency. However, all operational amplifiers have a finite bandwidth, generally called the “-3dB point,” where the gain begins to roll as frequency increases. The gain of the amplifier then decreases at a rate of -20dB/decade while the frequency increases. Op amps with a higher BW have improved performance because they maintain higher gains at higher frequencies; however, this higher gain results in larger power consumption or increased cost.

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/84e4b3e5-7a8c-4f47-891a-f6d538cf9f8f)

## Specifications for the Design
![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/4e60cd31-ee10-4e6e-b6fd-02959310349e)

## Simulation Procedure
* Step 1: Open the Cadence Virtuoso Design tool.
* Step 2: Create a new library using the CIW window (File -> New -> Library). Attach this library to the gpdk045nm technology node, or any other technology node.
* Step 3: Create a new cell view using the library manager window (File -> New -> Cell View). 
* Step 4: Start placing the components from the built-in analoglib component library.
  Components in the schematic:

  *  NMOS [nmos2v] (gpdk045)
  *  PMOS [pmos2v] (gpdk045)
  *  Voltage source VDD [vdd] = 1.8V (analoglib)
  *  Voltage source Vin [vin] = 0.9V DC + 1mV 1KHz Sine Wave (analoglib)
  *  Current source Iref [Iref] = 10uA (analoglib)
  *  Ground [gnd] (analoglib)

 Create the schematic as per the following circuit diagram:
![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/7f80062c-32e6-4f5a-bb00-a92908eca8c2)
Schematic for a 0.9V 2-stage opamp with Miller capacitor compensation and load

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/77309c72-b551-4a43-9b82-cf1d65e169cc)
Schematic for a 0.9V 2-stage opamp with Miller capacitor, Nulling resistor, and load

* Step 5: Launch ADE L for simulation
* Step 6: Choose the analysis method, then select the DC analysis and check the “save DC operating points” option.
* Step 7: Choose the analysis method, then select the Transient analysis and set the time from 0s to 10ms.
* Step 8: Choose the analysis method, then select the AC analysis and set the frequency from 1Hz to 10GHz.
* Step 9: Choose the analysis method, then select the Stability (stb) analysis and set the time from 1Hz to 10GHz.
* Step 10: Select the “outputs” menu and then the “To be plotted on schematic” option and select the net plots you want.
* Step 11: Check the simulation type and nets to be plotted in the ADE L and hit the netlist and run option (green play button). The simulation will start, and the simulation results will be printed.
* Step 12: To get a sweep for any of the DC simulations, set the sweep range of any parameter such as Vdd from 0 to 1.8V or temperature from -50C to 125C.

## Outputs
#### DC Operating Point Simulation: 2-Stage Opamp (Vout = 0.9V; VinDC = 0.9V, VinAC = 1KHz Sine wave w/2mVpp amplitude)
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/d0fb747c-1f0f-4253-b221-3d4582884981)

  Resultant DC operating points of a 2-stage opamp with miller compensation and load

#### DC Operating Point Simulation: 2-Stage Opamp with full compensation (Vout = 0.9V; VinDC = 0.9V, VinAC = 1KHz Sine wave w/2mVpp amplitude)
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/d0cb1907-4fcb-4254-8bce-cb0bafaf440f)

  Resultant DC operating points of a 2-stage opamp with full compensation and load

#### DC Simulation with a VDD sweep from 1.6V to 2V (VDD v/s VOUT: 2-Stage Opamp (Vout = 0.9V; VinDC = 0.9V, VinAC = 1KHz Sine wave w/2mVpp amplitude)
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/9ed5f5a8-5a54-409f-a91f-dcf7fae5db2f)

  Resultant waveforms for the VDD v/s Vout sweep of a 2-stage opamp with miller compensation and load

#### DC Simulation with a VDD sweep from 1.6V to 2V (VDD v/s VOUT: 2-Stage Opamp with full compensation (Vout = 0.9V; VinDC = 0.9V, VinAC = 1KHz Sine wave w/2mVpp amplitude)
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/6af976cc-18d4-46e4-9102-0f14adcad05a)

  Resultant waveforms for the VDD v/s Vout sweep of a 2-stage opamp with full compensation and load

#### 2-Stage Opamp Transient simulation [0-10ms] (VinDC = 900mV, VinAC = 1KHz Sine wave w/2mVpp amplitude):
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/8597aa4e-b790-48ce-95a6-3bb16912edec)

  Resultant waveforms for the Vin, ID and Vout of a 2-stage opamp with miller compensation and load

#### 2-Stage Opamp (with full compensation) Transient simulation [0-10ms] (VinDC = 900mV, VinAC = 1KHz Sine wave w/2mVpp amplitude):
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/a09a8008-000c-4035-a66c-47ee6dd49a05)

  Resultant waveforms for the Vin, ID and Vout of a 2-stage opamp with full compensation and load

#### 2-Stage Opamp Stability response (1 to 100GHz) - Magnitude and Phase plots: (LG = 55.97dB; PM = 48.52°; UGB at 7.92MHz):
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/f6c67c58-a46a-41f9-a438-7ac1d2a36b13)

  Resultant waveforms for the Stability Response of a 2-stage opamp with miller compensation and load

#### 2-Stage Opamp (with full compensation) Stability response (1 to 100GHz) - Magnitude and Phase plots: (LG = 54.94dB; PM = 59.51°; UGB at 7.83MHz):
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/9e7beedb-1682-4c39-a220-f198de44e06d)

  Resultant waveforms for the Stability Response of a 2-stage opamp with full compensation and load

## References
 - [1] https://web.mit.edu/6.101/www/reference/op_amps_everyone.pdf
 - [2] https://www.monolithicpower.com/en/operational-amplifiers
 - [3] https://ecstudiosystems.com/discover/textbooks/basic-electronics/operational-amplifiers/block-diagram/
 - [4] https://en.wikipedia.org/wiki/Operational_amplifier
