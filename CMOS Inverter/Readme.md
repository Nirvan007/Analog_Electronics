CMOS Inverter <a name="TOP"></a>
===================

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/c2e148e0-403b-4b48-bf46-40eaba7efb26)

## Table of Contents
* [Theory](#Theory)
* [Simulation Procedure](#Simulation-Procedure)
* [Outputs](#Outputs)
* [References](#References)

## Theory

### What is CMOS and an inverter in simple terms?
The term “CMOS” stands for “complementary-symmetry metal–oxide–semiconductor”. CMOS is a type of MOSFET, where its fabrication process uses complementary & symmetrical P-type & N-type MOSFET pairs for logic functions. The main CMOS devices characteristics are consumption of low static power & high noise immunity. The inverter is accepted universally as the basic logic gate while performing a Boolean operation on a single i/p variable. A basic inverter circuit is used to accomplish a logic variable by complementing from A to A’. So, a CMOS inverter is a very simple circuit, designed with two opposite-polarity MOSFETs within a complementary way. This article discusses an overview of the CMOS inverter and its working with applications.

### What is a CMOS Inverter?

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/6bb0eaea-1ef3-4fd5-8470-f6a2c98b915e)

It consists of a series connection of a PMOS and an NMOS. VDD represents the voltage of logic 1, while the ground represents logic 0. Whenever the input is high or 1, the NMOS is switched on while the PMOS is turned off. Thus output Y is directly connected to the ground and thus comes to be logic 0. When the input is logic 0, the reverse happens – NMOS goes off and PMOS goes on. This provides a direct path between VDD and output Y. Hence Y becomes high. This is the basic principle of operation of a CMOS inverter.

### CMOS Inverter Characteristics

Inverter Static Characteristics or VTC
The quality of the inverter can be measured frequently by using the VTC or voltage transfer curve, which is plotted between input voltage (Vin) and output voltage (Vo). From the following static characteristics, the parameters of devices like gain, operating logic levels & noise tolerance, and noise can be obtained.

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/ee7cab10-b34a-4ffb-9662-b7c7ae4d058b)

The VTC or voltage transfer curve looks like an inverted step-function that specifies accurate switching in between ON & OFF however in real devices, a gradual transition region exists. The voltage transfer curve specifies that for less input voltage Vin, the circuit generates high voltage Vout, whereas, for high input, it generates 0 volts. The transition region slope is a measure of quality – steep slopes yield exact switching. The tolerance toward noise can be calculated by evaluating the smallest input to the highest output for every region of ON or OFF operation.

Inverter Dynamic Characteristics
The CMOS inverter dynamic characteristics are shown below. So, some of the following formal definitions of different parameters are discussed below. Here, all the percentage (%) values are the steady-state values.

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/4b8adcd4-8af9-4479-a896-ee067d6072f1)

* Rise Time or tr: Rise time is the time used to increase the signal from 10% to 90%.
* Fall Time or tf: Fall time is the time used to drop the signal from 90% to 10%
* Edge Rate or trf : It is (tr + tf )/2.
* The propagation delay from high to low or tpHL: The time used to drop from VOH – 50%.
* The propagation delay from low to high or tpLH: The time used to increase from 50%- VOL.
* Propagation Delay or tp: It is (tpHL + tpLH)/2.
* Contamination Delay or tcd: It is the smallest time from the 50% input crossing to the 50% output crossing.

### Applications
The applications of CMOS inverters include the following.
* CMOS inverters are used in different ICs (integrated circuits) like microprocessors, static RAM, microcontrollers, data converters, image sensors & transceivers.
* These are found in mobile devices, digital cameras, home computers, cell phones, routers, network servers, modems & virtually each other electronic device that needs logic functions.

## Simulation Procedure
* Step 1: Open the Cadence Virtuoso Design tool.
* Step 2: Create a new library using the CIW window (File -> New -> Library). Attach this library to the gpdk045nm technology node, or any other technology node.
* Step 3: Create a new cell view using the library manager window (File -> New -> Cell View). 
* Step 4: Start placing the components from the built-in analoglib component library.
  Components in the schematic:
  
  *  NMOS [nmos2v] (gpdk045)
  *  PMOS [pmos2v] (gpdk045)
  *  Voltage source VDD [vdd] = 1.8V (analoglib)
  *  Voltage source Vin [vin] = 0.9V DC + 1mV 1KHz Sine Wave or Square wave(analoglib)
  *  Ground [gnd] (analoglib)

 Create the schematic as per the following circuit diagram:
 ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/8170cd95-7de9-4024-8b05-7b5c0eb0daa6)

 Create a symbol as per the following diagram:
 
 ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/926eb914-0c52-4e95-b715-01f05259e224)

 
 Create a testbench using the symbol as per the following diagram:
 ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/475df34f-e541-4905-9442-85b8a99272c0)

* Step 5: Launch ADE L for simulation
* Step 6: Choose the analysis method, then select the DC analysis and check the “save DC operating points” option.
* Step 7: Choose the analysis method, then select the Transient analysis and set the time from 0s to 10ms.
* Step 8: Select the “outputs” menu and then the “To be plotted on schematic” option and select the net plots you want.
* Step 9: Check the simulation type and nets to be plotted in the ADE L and hit the netlist and run option (green play button). The simulation will start, and the simulation results will be printed.
* Step 10: To get a sweep for any of the DC simulations, set the sweep range of any parameter such as Vin/Vdd from 0 to 1.8V or temperature from -50C to 125C.

## Outputs
#### CMOS Inverter Transient simulation [0-100ns] (VinDC = 1.8V, Pulse input Period = 20ns, Rise & Fall time = 50ps; Amplitude = 1V):
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/3330dacb-99c6-46df-a5d3-56f6843e1b0b)

  Graph for the Vin v/s Vout for the CMOS Inverter

## References
 - [1] https://www.elprocus.com/cmos-inverter/
 - [2] https://www.geeksforgeeks.org/cmos-logic-gate/
 - [3] https://electronics.stackexchange.com/questions/399192/cmos-inverter-based-question-from-sedrasmith-microelectronic-circuits
