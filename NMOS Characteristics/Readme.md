NMOS Characteristics <a name="TOP"></a>
===================

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/740b169c-9395-4215-8259-1e891805f6d0)


## Table of Contents
* [Theory](#Theory)
* [Simulation Procedure](#Simulation-Procedure)
* [References](#References)

## Theory
### Construction of N-Channel MOSFET

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/f889e0d2-9b23-4bbe-82f9-29df876609c5)

A lightly doped P-type substrate is taken into which two heavily doped N-type regions are diffused, which act as source and drain. Between these two N+ regions, occurs diffusion to   form an N-channel, connecting the drain and source. A thin layer of Silicon dioxide (SiO2) is grown over the entire surface and holes are made to draw ohmic contacts for drain and source terminals. A conducting layer of aluminum is laid over the entire channel, upon this SiO2 layer from source to drain which constitutes the gate. The SiO2 substrate is connected to the      common or ground terminals. Because of its construction, the MOSFET has a much smaller chip area than BJT, which is 5% of the occupancy when compared to the bipolar junction transistor. This device can be operated in modes. They are depletion and enhancement modes.

### Working of N-Channel MOSFET (Depletion mode)

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/21a06ae4-a6fc-4a35-a988-e368a388229f)

We can observe that, the diffused channel N between two N+ regions, the insulating dielectric SiO2, and the aluminum metal layer of the gate together form a parallel plate capacitor. If the NMOS has to be worked in depletion mode, the gate terminal should be at negative potential while the drain is at positive potential, as shown in the following figure. When no voltage is applied between the gate and the source, some current flows due to the voltage between the drain and the source. Let some negative voltage is applied at VGG. Then the minority carriers i.e. holes, get attracted and settle near the SiO2 layer. But the majority of carriers, i.e., electrons get repelled. With some amount of negative potential at VGG a certain amount of drain current ID flows from source to drain. When this negative potential is further increased, the electrons get depleted and the current ID decreases. Hence the more negative the applied VGG, the lesser the value of the drain current ID will be. The channel nearer to the drain gets more depleted than at the source like in FET and the current flow decreases due to this effect. Hence it is called depletion mode MOSFET.

### Working of N-Channel MOSFET (Enhancement mode)

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/79e1c1d5-a3a2-4fbf-8c7c-cd82192aad11)

The same MOSFET can be worked in enhancement mode, if we can change the polarities of the voltage VGG. So, let us consider the MOSFET with gate-source voltage VGG being positive as shown in the following figure. When no voltage is applied between gate and source, some current flows due to the voltage between drain and source. Let some positive voltage is applied at VGG. Then the minority carriers i.e. holes, get repelled and the majority carriers i.e. electrons get attracted towards the SiO2 layer. With some amount of positive potential at VGG a certain amount of drain current ID flows from source to drain. When this positive potential is further increased, the current ID increases due to the flow of electrons from the source, and these are pushed further due to the voltage applied at VGG. Hence the more positive the applied VGG, the more the value of drain current ID will be. The current flow gets enhanced due to the increase in electron flow better than in depletion mode. Hence this mode is termed as Enhanced Mode MOSFET.

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
 - [1] https://www.tutorialspoint.com/basic_electronics/basic_electronics_mosfet.htm
