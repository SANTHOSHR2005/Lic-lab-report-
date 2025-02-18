![image](https://github.com/user-attachments/assets/2b771e74-5486-4bf7-88b6-bac56833c34a)# Experiment: Common Source Amplifier in LTspice  

## Objective  
To design and analyze a common source amplifier using an NMOS transistor in LTspice and study its DC, AC, and transient response.  

## Components Required  
- NMOS transistor (M1)  
- Resistor (22.6kΩ)  
- DC voltage source (1.8V)  
- AC signal source (SINE 0.9V, 50mV, 1kHz)  

## Theory  


### NMOS Transistor Operation  
An NMOS transistor is a type of MOSFET where the majority charge carriers are electrons. It has three terminals: gate, drain, and source. The transistor operates in three regions:  

1. Cutoff Region – The MOSFET is off when the gate-to-source voltage is less than the threshold voltage, and no current flows.  
2. Triode Region – The MOSFET acts as a variable resistor when the gate voltage is high enough, allowing controlled current flow.  
3. Saturation Region – The MOSFET is fully turned on and operates as an amplifier, where small variations in gate voltage cause significant changes in drain current. 

Current drain equation for saturation region 

I_D = (1/2) * μ_n C_ox (W/L) * (V_GS - V_th)^2 * (1 + λ * V_DS) 

### Common Source Amplifier  
In this circuit, the NMOS transistor is configured as a common source amplifier. The input AC signal is applied to the gate, and the amplified output is taken from the drain. The resistor at the drain acts as the load, and the transistor’s operation determines the voltage gain.  

- The amplifier provides an inverted output signal compared to the input.  
- The voltage gain depends on the transistor's transconductance and drain resistance.  
- Proper biasing ensures the MOSFET remains in the saturation region for linear amplification.  


![image](https://github.com/user-attachments/assets/bdc2b719-7338-4dd7-b886-ade38aad8966)


## Procedure  
1. Open LTspice and create a new schematic.  
2. Add the NMOS transistor, resistor, DC voltage source, and AC signal source with appropriate values.  
3. Connect the components as per the circuit diagram.  
4. Run DC analysis to determine the biasing conditions.  Take .op
5. Perform AC analysis to observe the voltage gain and frequency response.  Take .ac dec 20 0.1 1T .

6. Execute transient analysis to visualize the amplifier's response over time.  Take .trans 5m
7. Analyze the output waveform to verify amplification.  

## Observation
DC ANALYSIS 

![image](https://github.com/user-attachments/assets/6029cd21-a98c-4218-be8d-06b9839323ad)

AC ANALYSIS

![image](https://github.com/user-attachments/assets/a24e67a4-7640-4344-a8dd-6f5f1a97cada)


Transient analysis 

![image](https://github.com/user-attachments/assets/c517f318-ff9b-4c6e-b7a6-c1e45b05f809)

 
## Inference  

1. DC Analysis determines the operating point of the MOSFET and ensures the transistor is in the correct region for amplification. The correct choice of gate voltage and resistor values is crucial for biasing.  
2. AC Analysis helps evaluate the voltage gain and frequency response of the amplifier. The gain depends on the transistor's properties and circuit components.  
3. Transient Analysis shows how the amplifier responds to time-varying input signals. The output waveform is an amplified and phase-inverted version of the input. 

Parametres used 
DC Analysis	Finds biasing conditions, DC voltages and currents	.op
AC Analysis	Finds gain vs frequency, bandwidth, cutoff frequency	.ac dec 20 0.1 1T
Transient Analysis	Finds time-domain response, waveform behavior	.tran 5m 



