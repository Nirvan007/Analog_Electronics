Differential Amplifier (5-Transistor Operational Transconductance Amplifier) <a name="TOP"></a>
===================

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/4e92f4c3-b7f3-42e7-9c41-bc294638cb50)

## Table of Contents
* [Theory](#Theory)
* [Procedure](#Procedure)
* [References](#References)

## Theory
### What is a differential amplifier?

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/ccddb144-d8d7-45d4-a855-ba7dbc6a099a)

* A MOSFET differential amplifier is a type of electronic amplifier that uses Metal-Oxide-Semiconductor Field-Effect Transistors (MOSFETs) as the active devices in its differential pair. The differential amplifier is a fundamental building block in analog circuit design and is commonly used in operational amplifiers, analog integrated circuits, and other applications.

### Why is a differential amplifier used?

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/21a06ae4-a6fc-4a35-a988-e368a388229f)

* Differential amplifiers apply gain not to one input signal but to the difference between two input signals. This means that a differential amplifier naturally eliminates noise or interference that is present in both input signals.
* Differential amplification also suppresses common-mode signals—in other words, a DC offset that is present in both input signals will be removed, and the gain will be applied only to the signal of interest (assuming, of course, that the signal of interest is not present in both inputs). This is particularly advantageous in the context of IC design because it eliminates the need for bulky DC-blocking capacitors.
* The subtraction that occurs in a differential pair makes it easy to incorporate the circuit into a negative-feedback amplifier, and if you’ve read the Negative Feedback series, you know that negative feedback is about the best thing that could ever happen to an amplifier circuit.

## Simulation Procedure
* Step 1: Open the Cadence Virtuoso Design tool.
* Step 2: Create a new library using the CIW window (File -> New -> Library). Attach this library to the gpdk045nm technology node, or any other technology node.
* Step 3: Create a new cell view using the library manager window (File -> New ->Cell View).
  
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/e256e176-e8b6-4fca-ba14-94e997f9a5d2)
  
* Step 4: Start placing the components from the built-in analoglib component library.
  Components in the schematic:
  1.	NMOS [nmos2v] (gpdk045)
  2.	Voltage source VGS [vdc] = 1.8V (analoglib) 
  3.	Voltage source VDS [vdc] = 1.8V (analoglib)
  4.	Ground [gnd] (analoglib)

 Create the schematic as per the following circuit diagram:

 ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/1830558c-4c6c-4549-9d43-7fbc9d0d7775)

* Step 5: Launch ADE L for simulation
* Step 6: Choose the analysis method and select the DC analysis and check the “save DC operating points” option.
  
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/057e0742-5fd0-4645-bbe5-7d6e27a4aad0)

* Step 7: Check the “Component Parameter” option and select the component “VGS” on the schematic. Set the sweep range from 0 to 1.8.
  
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/40fb246a-4352-4191-b5a8-c21903fd286c)

* Step 8: Select the “outputs” menu and then “To be plotted on schematic” option and select the NMOS Drain terminal.
  
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/e5f76407-f835-4936-b8bf-05a3dbdc9d7a)

* Step 9: Create a netlist.
  
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/668ac281-85e6-4a73-a6e4-f7bfad763ba4)

* Step 10: Go back to the ADE L and hit the netlist and run option (green play button). The simulation will start, and the simulation results will be printed.
  
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/88958dd1-25f8-4ac8-a0d0-dd2100361757)
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/8a8778c1-4dcd-4b30-ba04-9dad3dfd0152)

* Step 11: Output I-V Characteristic (Id vs Vgs) graph for the NMOS with a sweep range of 0 to 1.8V.
  
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/8437a456-3ccf-403a-bbe0-97418cde8e7c)

* Step 12: Check the “Component Parameter” option and select the component “VDS” on the schematic. Set the sweep range from 0 to 1.8.
  
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/384d73a0-cab2-41d6-b082-562f86eb8b0b)

* Step 13: Select the “outputs” menu and then “To be plotted on schematic” option and select the NMOS Drain terminal.
  
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/58fa86a8-c213-4177-9392-1c8f4c93a482)

* Step 14: Output I-V Characteristic (Id vs Vds) graph for the NMOS with a sweep range of 0 to 1.8V.
  
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/84912f17-24ba-43aa-83bd-846f695c742b)

## References
 - [1] [https://www.tutorialspoint.com/basic_electronics/basic_electronics_mosfet.htm](https://www.elprocus.com/differential-amplifier-circuit-using-transistors/)https://www.elprocus.com/differential-amplifier-circuit-using-transistors/
 - [2] https://www.allaboutcircuits.com/technical-articles/the-basic-mosfet-differential-pair
 - 
