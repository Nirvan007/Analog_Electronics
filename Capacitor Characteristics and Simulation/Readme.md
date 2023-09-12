Capacitor Voltage Transfer Characteristics <a name="TOP"></a>
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
  * [Transient](#Transient)

## Description
* The schematic and simulation of a capacitor was performed using Cadence Virtuoso Layout Suite in a Linux environment.

## Aim
* To simulate the VTC of a capacitor with a constant current source and a supply voltage of constant 2V DC.

## Calculations
![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/2a73449e-8658-4901-adfc-a49da464aed1)

## Procedure
* Open the Command Interface and create a new library
* Give a name to the library (eg. `ACD_June23_batch`)
* Select the “`attach to an existing technology`” node option
* Select the "`gpdk 90nm`" technology node
* Select the cell
* Add a new cell by going to the "`files/new/cell`" option
* Give a name to the cell (`eg. test_schematic`) and click “`OK`” keeping all other options as default.
* After clicking on the “`OK`” button, the schematic will open
* To get an instance, click the “`I`” button on the keyboard which will open the instance tab
* Search the required component in the cell option and click the “`symbo`l” option.
* Now there will be a component floating in the matrix
* Press “`ESC`” to deselect the component
* Select multiple by holding "`left click`" on the mouse and delete using the delete option
* Press "`F`" to fit (zoom) the component
* Press "`W`" for wire
* To copy the component click “`C`” and then tap the component that has to be copied.
* To move the components click “`M`” on the keyboard and then tap on the component
* Tap on the component and Press “`Q`” to change the parameters
* To open the simulation tab, go to the “`Launch`” option on the top left and select the “`ADE L`” option
* Right-click on the “`design variables window`” and select the “`copy from cell view`” option
* Click on the "`AC/DC/Trans analyses`" option on the top right
* To save the parameters or state, go to the “`Sessions`” option and then click the “`save state`” option
* Save the file in the required directory (`eg. ACD_June23_batch/test_schematic_/spectre/saved_state1`)
* To change the simulator, go to the "`setup`" option and then select the simulator option
* For high-performance simulations go to high-performance simulations in the setup option then APS (uses multiple licenses and multi-threading)
* Temperature can also be changed using the "`temp C`" option
* To save the outputs, go to "`outputs`" and select the specific saving only the required outputs. All can also be saved but takes more time
* To perform a simulation, go to the “`Simulation`” option and then click the “`Netlist and Run`” option
* The simulation will begin and then it will print the outputs in another tab
* To set the initial conditions, select the net and set net with a initial condition and then assign the value

## Schematic
![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/dc91eb91-faa0-4a91-a3c1-4239b302f577)

## Netlist
![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/979bb477-4d9b-4fba-a873-b92f3e10ff96)

## Analyses
![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/c8945ee2-221d-40ef-84bc-25117df56fa3)

### DC
![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/bc5561ab-cc39-422a-9c4e-c8e55b93b106)

### Transient
![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/08148d57-24fa-41d0-b471-66ece271dd83)

## Output VTC Graph
![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/48ac65c5-dd8a-4f2b-a36f-905e3e3bd5e3)
![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/5baa6c75-1fc2-4ce7-910f-ca6346a1b42a)

## Conclusion
* As calculated in theory, the practical simulation results were the same, that is after a transient analysis of 1ms delay, the capacitor charges linearly until it reaches the 1V mark.
