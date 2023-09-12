PMOS Characteristics <a name="TOP"></a>
===================

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/b0939c40-c3b8-41df-9476-8cb442027029)

## Table of Contents
* [Theory](#Theory)
* [Procedure](#Procedure)
* [References](#References)

## Theory
* Construction of P-Channel MOSFET

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/7f032ffb-329d-48b9-bc64-c7f38134e7e3)

* The construction and working of a PMOS is the same as NMOS. A lightly doped n-substrate is taken into which two heavily doped P+ regions are diffused. These two P+ regions act as source and drain. A thin layer of SiO2 is grown over the surface. Holes are cut through this layer to make contact with P+ regions, as shown in the following figure.

* Working of P-Channel MOSFET (Depletion mode)

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/2fb69521-934c-40fb-b857-752b93079087)

* The p channel depletion MOSFET construction is reversed to n channel depletion MOSFET. The channel in this MOSFET is pre-build because of the available p-type impurities in it. Once the negative (-) voltage is applied at the gate terminal then the minority charge carriers like electrons in the n-type get attracted towards the p-type channel. In this condition, once a drain is reverse biased then the device begins conducting although, when the negative voltage within the drain is enhanced then it results in the depletion layer formation.

This region mainly depends on the layer concentration formed because of the holes. The depletion layer’s region width will affect the conductivity value of the channel. So, by variations of the region’s voltage values, the flow of current gets controlled. At last, the gate & the drain will stay at the negative polarity while the source remains at the ‘0’ value.

* Working of P-Channel MOSFET (Enhancement mode)

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/b39b0460-7b1b-4c30-9928-8c102fa1f7ee)

* The p channel enhancement MOSFET is simply designed with a lightly doped n-substrate. Here, two p-type materials with heavily doped are separated through the channel length like ‘L’. The thin silicon dioxide layer is deposited on the substrate which is normally called the dielectric layer. When a negative voltage is applied to the gate (G) terminal then the +ve concentration of the charges will be settled under the dielectric layer due to the capacitance effect. The electrons available at the n substrate because of the repulsive forces will get moved. When a negative voltage is applied at the drain terminal then negative voltage within the drain region decreases the voltage difference between gate & drain decreases, thus, the conductive channel width gets decreased toward the drain region, and current supplies from source to drain. The channel formed within the MOSFET provides resistance to the flow of current from source to drain. Here, the resistance of the channel mainly depends on the side view of the channel & again this channel’s cross-section depends on the negative voltage applied at the gate terminal. Thus the current flow from the source to the drain can be controlled through the voltage applied at the gate terminal so MOSFET is known as a voltage-controlled device. When the hole concentration forms the channel & the flow of current throughout the channel gets improved because of an increase within negative gate voltage, this is known as P – Channel Enhancement MOSFET.

## Simulation Procedure
* Step 1: Open the Cadence Virtuoso Design tool.
* Step 2: Create a new library using the CIW window (File -> New -> Library). Attach this library to the gpdk045nm technology node, or any other technology node.
* Step 3: Create a new cell view using the library manager window (File -> New ->Cell View).
  
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/62cbf04e-ecd0-4cd6-9ec5-1119b28ae2ff)

* Step 4: Start placing the components from the built-in analoglib component library.
  Components in the schematic:
  1.	PMOS [pmos2v] (gpdk045)
  2.	Voltage source VGS [vdc] = 1.8V (analoglib) 
  3.	Voltage source VDS [vdc] = 1.8V (analoglib)
  4.	Ground [gnd] (analoglib)

  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/20a18118-ba1e-4e1a-9462-4e8590e8d030)

* Step 5: Launch ADE L for simulation
* Step 6: Choose the analysis method, select the DC analysis, and check the “save DC operating points” option.

  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/156f805a-4917-4589-8986-a54fc67d8999)

* Step 7: Check the “Component Parameter” option and select the component “VGS” on the schematic. Set the sweep range from 0 to 1.8V.

  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/5740557f-07ec-4da3-b0fc-29c4dea77e90)

* Step 8: Select the “outputs” menu and then “To be plotted on schematic” option and select the PMOS Source terminal.

  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/8e98654e-d4aa-4668-ad08-cb511c6c4a02)

* Step 9: Create a netlist.

  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/1e323f16-5435-4983-84b8-4b19133fd0e2)

* Step 10: Go back to the ADE L and hit the netlist and run option (green play button). The simulation will start, and the simulation results will be printed.

  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/3e231d06-b667-4293-b3d5-5924614a7813)
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/3cde2e66-4a35-4884-bc58-2c754b122012)

* Step 11: Output I-V Characteristic (Id vs Vgs) graph for the PMOS with a sweep range of 0 to 1.8V.

  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/3d019267-efaf-4425-8e31-74c834171315)

* Step 12: Check the “Component Parameter” option and select the component “VDS” on the schematic. Set the sweep range from 0 to 1.8V.

  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/cf1f432a-ecb9-476d-9337-00b06121ed77)
  
* Step 13: Select the “outputs” menu and then “To be plotted on schematic” option and select the PMOS Source terminal.

  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/5bdcf5fd-cbca-4e75-8c5b-6d8c13292399)

* Step 14: Output I-V Characteristic (Id vs Vds) graph for the NMOS with sweep range of 0 to 1.8V.

  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/72f5b1e2-cdd0-4d49-b731-8d540e037f40)

## References
 - [1] https://www.tutorialspoint.com/basic_electronics/basic_electronics_mosfet.htm#
 - [2] https://www.elprocus.com/p-channel-mosfet/
