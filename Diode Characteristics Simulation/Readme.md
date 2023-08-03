Diode Characteristics <a name="TOP"></a>
===================

## Table of Contents
* [Description](#Description)
* [Aim](#Aim)
* [Calculations](#Calculations)
* [Procedure](#Procedure)
* [Schematic](#Schematic)
* [Netlist](#Netlist)
* [Analyses](#Analyses)
  * [DC](#DC)
  * [AC Transient](#AC-Transient)
* [Source](#Source)
* [References](#References)
* [Acknowledgement](#Acknowledgement)

## Description
* The schematic and simulation of a P-N junction diode were performed using Cadence Virtuoso Layout Suite in a Linux environment.

## Aim
* To simulate the characteristics of a diode with a constant voltage source of 0.8V DC was used and a 1Kohm resistor in series.

## Theory
### What is a Diode?
A diode is an electronic device having a two-terminal unidirectional power supply i.e. it has two terminals and allows the current to flow only in one direction. Diodes are widely used in modern-day circuits to secure circuits from over-voltage and they are also used to change AC current to DC current.

### Representation Symbol of a Diode
Diodes are represented using special symbols and the symbol for a standard diode symbol is given below. In the given diagram it is clear that a diode has two terminals which are called the cathode and anode. The arrowhead symbol represents the anode and the other end represents the cathode. The current flow from cathode to anode in the forward bias condition. The general representation of a Diode is given below,

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/1c6969c6-d3ae-4d33-8e04-cbc6c4208a4b) 

### Construction of Diode
We know that there are two types of semiconductor materials: Intrinsic and Extrinsic semiconductors. In intrinsic semiconductors, the number of electrons and hole concentration are equal at room temperature. In an extrinsic semiconductor, impurities are added to the semiconductor to increase the number of electrons or the number of holes. These impurities are pentavalent (Arsenic, Antimony, phosphorous) or tri-valent (boron, indium, aluminium).

A semiconductor diode has two layers. one layer is of p-type and the other is of n-type semiconductor.

* If we add trivalent impurities in a semiconductor (Silicon and germanium), a greater number of holes are present and it is a positive charge. therefore this type of layer is known as the p-type layer.
* If we add pentavalent impurities in semiconductors (silicon or germanium), due to excess electrons there is a negative charge. therefore this type of layer is known as the n-type layer.

### Working of Diode
* In the N-type region, the majority of charge carriers are electrons and the minority of charge carriers are holes. Whereas, In the P-type region, the majority of charge carriers are holes and the minority of charge carriers are electrons. Because of the concentration difference, the diffusion takes place in majority charge carriers and they recombine with the minority charge carriers which are then collected near the junction and this region is known as the Depletion Region.

* When the anode or p-type terminal of the diode is connected with a negative terminal and the n-type or cathode is connected with the positive terminal of a battery, this type of connection is called a Reverse Bias condition.

* When the anode or p-type terminal of the diode is connected with a positive terminal and the n-type or cathode is connected with the negative terminal of the battery, this type of connection is called a Forward Bias condition.

### Characteristics of Diode
The characteristics of the diode can easily be understood under the following three headings.

* Forward-Biased Diode
* Reverse-Biased Diode
* Zero Biased Diode OR Unbaised Diode

* Forward-Biased Diode
  In forward biasing semiconductor is connected to an external source when the p-type semiconductor is connected to the positive terminal of the source or battery and the negative terminal to the n-type, then this type of junction is said to be forward-biased. In forward bias, the direction of the built-in electric field near the junction and the applied electric field are opposite in direction. This means that the resultant electric field has a magnitude lesser than the built-in electric field due to this there is less resistivity and therefore depletion region is thinner. In silicon, at the voltage of 0.6 V, the resistance of the depletion region becomes completely negligible.

* Reverse-Biased Diode
  In reverse biasing, the n-type is connected to the positive terminal, and the p-type is connected to the negative terminal of the battery. In this case, the applied electric field and the built-in electric field are in the same direction and the resultant electric field has a higher magnitude than the built-in electric field creating a more resistive, therefore depletion region is thicker. if the applied voltage becomes larger, then the depletion region becomes more resistive and thicker.

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/c8292aec-e3b9-4257-83c1-b84bc24d7a95)

## Source
For more information please visit https://www.geeksforgeeks.org/diode/

## Procedure
Step 1: Open the Cadence Virtuoso Design tool.
Step 2: Create a new library using the CIW window (File -> New -> Library). Attach this library to the gpdk045nm technology node, or any other technology node.
* ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/57809c6f-8723-4d33-bce6-aaa28984dd21)

Step 3: Create a new cell view using the library manager window (File -> New ->Cell View).
* ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/406aac6b-b968-4e1c-9784-ec3ee15a52f9)

Step 4: Start placing the components from the built-in analoglib component library.
* Components in the schematic:
  1.	Diode [ndio]
  2.	Voltage source [vdc] = vd (analoglib) {V = 0.8v to be set in ADE L}
  3.	Ground [gnd] (analoglib)
  4.	Resistor [res] = 1K (analoglib)
* ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/93e7e361-e0b8-449a-82f5-61df630c5ae3)

Step 6: Connect the components as per the following circuit diagram.
* ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/1a433c8a-9386-46e1-b1f2-79d0a1e955bf)

Step 7: Launch ADE L for simulation
Step 8: Copy the variables from the cell view and set the value of vdc = vd = 800mV.
* ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/102246aa-3220-4bdc-92e8-e68af602c0a0)

Step 9: Choose the analysis method and select the DC analysis and check the “save DC operating points” option.
* ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/2bd0b683-f60f-4112-9cca-7365880bc858)

Step 10: Check the “design variable” option and select the variable “vd”. Set the sweep range from 0 to 1.4.
* ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/4ecb6fb2-e647-4b76-988f-603380a4e0dd)

Step 11: Select the “outputs” menu and then “To be plotted on schematic” option and select the diode’s positive terminal.
* ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/f73dacc0-ec5b-403d-821d-b26dc424375b)
* ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/bf11e79c-bcd0-4404-aa73-016fe66a4e56)

Step 12: Create a netlist.
* ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/16f7b199-27a7-4466-aced-b1a00e1c5f24)

Step 13: Go back to the ADE L and hit the netlist and run option (green play button). The simulation will start, and the simulation results will be printed.
* ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/121d20ca-5b0b-4b74-a536-e0af1144de31)
* ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/cadafbc6-c63d-4eb7-b9b0-06d6cd7e8646)
* ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/140842d3-16d7-4483-9852-c6ff899d8f62)
* ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/20c3a5dc-d622-453a-82e0-ab53c8611797)
* ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/a57f3cc2-7113-4976-9e4e-9ae9f6d8c147)

Step 14: Observe the Output graph for 0 to 1.4v (Forward bias)
* ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/3393c5aa-30f1-431a-839b-5d263bb9b853)

Step 15: Edit the DC analysis parameters for a sweep range of 0 to -1.4v
* ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/9deeb714-f1e1-4e9c-a031-6101870e8c15)

Step 16: Observe the Output graph for 0 to -1.4v (Reverse bias)
* ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/f6d435f9-0044-40f7-a9dc-8d33f47f64b8)

## Conclusion
* Thus from the resultant outputs, we can conclude that, when the diode is supplied with a voltage greater than 0.8V, it enters the forward bias mode and starts conducting.

## References
 - [1] https://www.geeksforgeeks.org/diode/
