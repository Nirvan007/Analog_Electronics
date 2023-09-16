Design of a Single-stage CS NMOS amplifier <a name="TOP"></a>
===================

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/7c65ddd7-b979-447d-a308-9d3885322047)


## Table of Contents
* [Theory](#Theory)
* [Design Example](#Design_Example)
* [Procedure](#Procedure)
* [Conclusion](#Conclusion)
* [References](#References)

## Theory
### What is a Common source amplifier?

A common-source (CS) MOSFET amplifier is a type of electronic circuit that uses a MOSFET to amplify an input AC signal. It's one of the most commonly used amplifier configurations in integrated circuit design.

### Components of a CS amplifier include:

* MOSFET: The heart of the CS amplifier is an n-channel MOSFET. This transistor has three terminals: the gate (G), the drain (D), and the source (S) (The body or the bulk terminal is shorted to the ground). It operates as a voltage-controlled current source.
* DC Biasing: The CS amplifier sets a specific DC biasing point (also called the Q-point) for the MOSFET. This DC biasing ensures that the transistor is in its active or saturation region. It's important because it allows the transistor to respond to small AC signals while avoiding distortion.
* Coupling Capacitors: To isolate the DC biasing from the input and output signals, coupling capacitors (Cin and Cout) are used. These capacitors block the flow of DC but allow AC signals to pass through.

### Working of a CS amplifier

The MOSFET is biased by setting a fixed DC voltage at its gate (VGS). This voltage determines the operating point of the transistor. By adjusting VGS and other components, we set the Q-point to ensure that the transistor operates in its active or saturation region, typically with a small drain current (ID).

When an AC signal (usually a small voltage variation around the DC bias) is applied to the gate of the MOSFET, it creates an AC voltage at the transistor's gate called VGS(ac).
VGS(ac) causes a small variation in the drain current (ID). This change in ID is directly proportional to the change in VGS(ac) and is governed by the transistor's transconductance (gm).

The variation in Id creates a voltage drop across the drain resistor (RD) according to Ohm's law (VD = ID * RD). The output voltage (Vout) is taken from this voltage drop across RD. Therefore, Vout represents the amplified AC version of the input signal.

The input coupling capacitor (Cin) blocks any DC component from reaching the gate, ensuring that only the AC signal gets amplified. The output coupling capacitor (Cout) blocks the DC component from the output, providing only the AC amplified signal to the load or the next stage of the circuit.

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/fda0b1c7-3049-45cb-b6f6-1726173f4577)

### How to find out gain Av?

#### Method 1:
By using Vout equation
Vout = VDD - IDRD  ------------------------------------------------------------------- [ro is not considered here]

Vout = VDD - {1/2 * UnCox * W/L * (VGS - VTH)2 * (1 + λVDS)} * RD

Differentiating on both sides, we get,
(δ Vout)/(δ Vin) = 0 - {1/2 * UnCOX * W/L * 2(VGS - VTH) * RD}

(δ Vout)/(δ Vin) =  - UnCOX * W/L * (VGS - VTH) * RD

(δ Vout)/(δ Vin) = -gm * RD --------------------------------------------------- [Since gm = UnCOX * W/L * (VGS - VTH)]

AV = -gm * RD

#### Method 2:
By the small signal model

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/8de9f256-9c9d-4348-b821-df830400386c)

Applying KCL at drain node, we get,

gmVin + Vout/ro + Vout / RD = 0

gmVin = - Vout * ( 1/ro + 1 / RD )

Vout/Vin = - gm / (1/ro + 1 / RD)

Vout/Vin = - gm * RD || ro

AV = - gm * RD || to

## Design Example:
Let’s design our own single-stage common source amplifier!

### Specifications:
Design a single-stage common source amplifier for a gain of -3 where the input signal is a sine wave of 100KHz having 2mV pp amplitude with a DC voltage of 0.6V. The supply voltage provided is 1.8V and the drain current must be less than 10uA. Design the schematic and simulate using transient, DC, and sweep analysis.

Changes: Add source degeneration to increase the gain if the gain is less than -3 and change the W/L ratio keeping ID less than 10uA.

#### Parameters given:
Av = -3
Vin(DC) = 0.6V
Vin(ss) = 10KHz 2mVpp sine wave
VDD = 1.8V
ID < 10uA

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/7324e60b-d662-40a8-bd12-fee5b69bd523)

#### Select the NMOS device for the design: 
Here the NMOS2v_3 device in the gpdk045 library can be selected which has 3 terminals (bulk is shorted to GND).

VTH ≈ 0.450V
UnCox ≈ 250 uS/V2 

Note: These values have been calculated by keeping the W/L ratio as 1/1 with a measurement of 1um/1um for the Length and Width of the MOSFET.

#### Calculate the Vout for this CS amplifier: 
Here the Vout can be calculated by using the formula for gain Av, where,

Av = -gm * (RD || ro)
Av = -gm * RD ------------------------------------------------------------------------ [Since ro << ]
Av = -(2 * ID / VDS) * RD  ----------------------------------------------------------- [Since gm = (2 * ID / VDS)]
Av = -{(2 * ID) / (VGS - VTH)} * RD ------------------------------------------------- [Since VDS ≥ (VGS - VTH)]

Av = -(2 * IDRD) / (VGS - VTH)
VD = IDRD = - {Av * (VGS - VTH)} / 2
VD = - {-3 * (0.600 - 0.450)} / 2
VD = 0.225V

Vout = VDD - (IDRD)
Vout = VDD - VD
Vout = 1.8 - 0.225
Vout = 1.575V

To maintain the MOSFET in saturation,
VDS ≥ (VGS - VTH)
VDS ≥ (0.600 - 0.450)
VDS ≥ 0.150

#### Calculate the approximate value of Gm,
gm = (2 * ID) / VDS = (2 * 10u) / 0.150
gm = 133.33 uS

#### Calculate the approximate value of Rout,
Rout = RD || ro
Rout = RD  ------------------------------------------------------------------- [Since we are not considering ro]
RD = VD / ID 
RD = 0.225 / 10u 
RD = 22.5KΩ

#### Calculate the W/L ratio for the MOSFET
Now that we have all the required values, we have to calculate the W/L value for the MOSFET:
Here we use the channel length modulation equation for ID,

ID = 1/2 * UnCox * W/L * (VGS - VTH)2 * (1 + λVDS)
ID = 1/2 * UnCox * W/L * (VGS - VTH)2 ---------------------------------------------------- [Consider λ = 0]

10u = 1/2 * 250u * W/L * (0.600 - 0.450)2
W/L = (10u * 2) / {250u * (0.600 - 0.450)2}
W/L = 3.56
W = L * 3.56

## Simulation Procedure
* Step 1: Open the Cadence Virtuoso Design tool.
* Step 2: Create a new library using the CIW window (File -> New -> Library). Attach this library to the gpdk045nm technology node, or any other technology node.
* Step 3: Create a new cell view using the library manager window (File -> New ->Cell View).
* Step 4: Place the components from the built-in analoglib component library.
  Components in the schematic:
  1.	NMOS [nmos2v_3] (gpdk045)
  2.	Resistor RD = 22.5KΩ (analoglib)
  3.	Voltage source VGS [vdc] = 1.8V (analoglib) / Add a vin input pin which has to be given a stimuli
  4.	Voltage source VDS [vdc] = 1.8V (analoglib) / Add a vdd input pin which has to be given a stimuli
  5.	Add a vout output pin which has to be given a stimuli
  6.	Ground [gnd] (analoglib)

Create the schematic as per the following circuit diagram:
Case 1:
L = 200nm
W = 200n * 3.56 = 712nm 
W ≈ 720nm

![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/7f24fd57-ce77-40fb-aaa7-6a4e10dae6e7)

* Step 5: Launch ADE L for simulation
* Step 6: Choose the analysis method, select the DC analysis, and check the “save DC operating points” option.
* Step 7: Choose the analysis method, select the Transient analysis, and set the value to 100us. Also, check the moderate-type simulation option.
  
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/534e9457-bf2c-4171-a5f8-ef6c6ec1f01e)

* Step 8: Select the “outputs” menu and then “To be plotted on schematic” option and select the vin pin and vout pin. You can select the drain terminal of the NMOS to see the ID waveform as well.
  
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/b56bcc9f-0196-4451-8eed-04b5a7f43966)

* Step 9: Set the stimuli.

  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/bbfa1447-78e4-4355-912d-7fa244275bc5)

* Step 10: Click the netlist and run option (green play button). The simulation will start, and the simulation results will be printed. (Annotate results in the ADE L must be selected to view the DC operating points)

* Step 11: Output waveforms for the CS amplifier's vin, vout, and ID.
  
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/2addb7b9-8a90-41ef-a656-8ef2fdb9b04e)
  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/489030f2-a99e-4516-90cc-d70f52a2e0be)

  Output calculations:
  ID = 8.703uA
  gm = 102.658uS
  
  δ Vout = 1.60651 - 1.60215
  δ Vout = 4.36 mV pp
  
  δ Vin = 0.60100 - 0.59900
  δ Vin = 2mV pp
  
  AV = (δ Vout)/(δ Vin) = 4.36/2
  AV = -2.18
  
  Here the gain was expected to be -3, but we are getting a gain of only -2.18. 
  This is because we have not considered the ro which is parallel to the resistor RD which in total constitutes Rout. 
  
  What can we do to increase AV?
  To increase the gain, the Rout parameter can be adjusted. Which is, the Rout that can be increased by increasing the value of resistor RD to 25KΩ.

* Step 12: We increase the value of resistor RD to 25KΩ
  Output waveform when R = 25KΩ:

  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/94904888-c409-4e12-9d14-eb89c9554a12)

  Output calculations:
  ID = 8.659uA
  gm = 102.339uS
  
  δ Vout = 1.58595 - 1.58115
  δ Vout = 4.8 mV pp
  
  δ Vin = 0.60100 - 0.59900
  δ Vin = 2mV pp
  
  AV = (δ Vout)/(δ Vin) = 4.80/2
  AV = -2.4
  
  
  Q: So is there any way that we can increase the gain a bit more?
  A: Yes, there is a way that we can increase the gain without changing the Rout of the circuit. We can increase the sizing of the MOSFET which will increase the gm and ro of the MOSFET     which will in turn increase the gain.

* Step 13: Increase the W & L of the NMOS

  Case 2: Now we take the W and L values as,
  L = 300nm
  W = 300n * 3.56 = 1068nm 
  W ≈ 1um

* Step 14: Plot the Output waveform when L = 300nm and W = 1um:

  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/4b43bc7c-4dea-4225-90a3-fcc0d79a673c)

  Output calculations:
  ID = 9.547uA
  gm = 108.623uS
  
  δ Vout = 1.5613 - 1.55875
  δ Vout = 5.11 mV pp
  
  δ Vin = 0.60100 - 0.59900
  δ Vin = 2mV pp
  
  AV = (δ Vout)/(δ Vin) = 5.11/2
  AV = -2.56
  
* Step 15: Increase the W & L a bit more,

 Case 3: Now, since there is still room for improvement, we double the initial W and L values from 200nm and 720nm to,
  L = 400nm
  W = 200n * 3.56 = 712nm 
  W ≈ 1.5um
  
  Output waveform when L = 400nm and W = 1.5um:

  ![image](https://github.com/Nirvan007/Analog_Electronics/assets/127144315/c2d44466-45f6-48e5-a4aa-febd43db908e)

  ID = 11.768uA
  gm = 131.037uS
  
  δ Vout = 1.5091 - 1.5029
  δ Vout = 6.2 mV pp
  
  δ Vin = 0.60100 - 0.59900
  δ Vin = 2mV pp
  
  AV = (δ Vout)/(δ Vin) = 6.2/2
  AV = -3.1
  
  Here the gain has come out to be higher than expected, that is, -3.1. But if you look carefully, the ID has increased to 11.768uA which is above the permissible design limit of 10uA.
  
## Conclusion: 
Therefore, the maximum gain that can be achieved with these specifications is approximately -2.56. There is still more room for improvement in this design, but to keep this analysis short I will be ending it here!
 
## References
 - [1] Behzad Razavi - Design of Analog CMOS Integrated Circuits
