# LIC-experiment
# Experiment – 01  
## LTspice Simulation of Common Source Amplifier

---

## 1. Aim of the Experiment  

The aim of this experiment is to analyze the operation of a Common Source (CS) MOSFET amplifier using LTspice. The circuit is studied using DC, transient, and AC analyses to understand its biasing condition, time-domain behavior, and frequency response. The simulation results are used to verify the theoretical characteristics of a common source amplifier.

---

## 2. Circuit Description  

The circuit uses a single NMOS transistor in a common source configuration. A resistor is connected at the drain as the load, while the source terminal is grounded. A DC supply provides biasing, and a small AC signal is applied at the gate to observe amplification.

### Components Used
- NMOS transistor (TSMC 180 nm technology)  
- Drain resistor (3 kΩ)  
- DC voltage source (1.2 V)  
- AC input voltage source  
- Ground and connecting wires  

---

## 3. Circuit Setup  

The circuit is designed in LTspice using the common source topology. The gate terminal is given a DC bias along with a small AC signal. Variations in drain current are converted into output voltage across the drain resistor. The output is taken from the drain terminal.

---

## 4. Experimental Procedure  

1. Draw the common source amplifier circuit in LTspice.  
2. Set the supply voltage to 1.8 V and gate bias to 0.9 V.  
3. Download the TSMC 180 nm MOSFET library and save it in the project folder.  
4. Include the library using the `.lib` directive.  
5. Select the NMOS model and assign suitable width and length values.  
6. Calculate the drain current based on the given power limit.  
7. Adjust the MOSFET width until the simulated drain current matches the calculated value.  
8. Run DC operating point analysis to verify voltages and current.  
9. Perform transient analysis using a sinusoidal input signal.  
10. Carry out AC analysis to obtain gain and phase response.

---

## 5. Calculations  

Given power limit:  
P = 0.4mW  

Using the relation:  
P = V × I  

Drain current:  
ID = 0.4 mW / 1.2 V ≈ 333.33 µA  

Drain voltage calculation:  
VDD = ID × RD + Vout  

Vout = 1.2 /2 = 0.6 V  

Q-point of the amplifier:  
(Vout, ID) = (0.6 V, 200 µA)

---
Circuit Diagram:
Without capacitor:
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/e4a4e45e-afd4-47df-90c6-e6834ea6b40d" />
With Capacitor:
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/509c9425-da85-4bff-997c-c6850544c337" />



## 6. DC Analysis  

DC analysis is used to confirm that the MOSFET operates in the saturation region. Saturation occurs when the drain-source voltage is greater than the overdrive voltage (VGS − VTH). The obtained operating point confirms proper biasing, which is required for amplification.

DC operating Point:

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/06f95933-16f2-41e1-82b7-6a8b75547649" />
DC Sweep:
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/5d587ed1-9ed1-4575-a930-750313a5b566" />


---

## 7. Transient Analysis  

Transient analysis shows the response of the amplifier to time-varying signals. A sinusoidal input is applied at the gate, and the output waveform at the drain is observed. The output is amplified and inverted, confirming the inverting nature of the common source amplifier.
Input:
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/bbc15c25-d17e-4245-b235-e380d9c27ae5" />

Output:
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/0d4906fb-7448-4c3c-abcf-5fb6a2c79252" />

Both:
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/19975731-5f3d-4a6b-87e9-929e73ab0acc" />

---

## 8. AC Analysis  

In AC analysis, the MOSFET is treated as a small-signal device. Small variations in gate voltage produce proportional changes in drain current. The voltage gain is given by:

Av = −gm (RD || RL)

The negative sign indicates a 180° phase shift between input and output. The gain remains constant at low frequencies and decreases at high frequencies due to parasitic capacitances.
Without capacitor:
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/eeec0433-aa40-414a-a490-28e98be0950f" />
With Capacitor:
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/5328f440-56c8-4cf9-b7ca-c42ad79dc4bf" />



---

## 9. Results Summary  

### DC Analysis  
- Drain current ≈ 200uA  
- Output voltage ≈ 0.6 V  
- MOSFET operates in saturation  

### AC Analysis  
- Voltage gain observed  
- Gain decreases at higher frequencies  
- Phase shift approaches −180°  

### Transient Analysis  
- Output signal is inverted  
- Clear amplification observed  
- Minor phase deviation due to non-ideal effects  

---

## 10. Conclusion  

The Common Source amplifier was successfully simulated using TSMC 180 nm technology in LTspice. DC analysis confirmed proper biasing and saturation-region operation. Transient and AC analyses verified signal amplification, phase inversion, and expected frequency response. The results closely match theoretical behavior of a common source amplifier.

---