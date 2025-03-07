# Experiment-3: MOS Differential Amplifier Design and Analysis

## Objective
To design and evaluate a MOS differential amplifier circuit based on given parameters, performing DC analysis, transient analysis, and frequency response assessment to extract key performance characteristics.

---

## Given Parameters
- **Supply Voltage (VDD):** 1.8V
- **Maximum Power Consumption (P):** 2mW
- **Common-Mode Input Voltage (Vicm):** 0.95V
- **Common-Mode Output Voltage (Vocm):** 1.09988V
- **Peak Voltage (Vp):** 0.4V

---

## Overview of MOS Differential Amplifier
A MOS differential amplifier consists of two MOSFETs (M1 and M2) sharing a common source connection. When different voltage signals are applied at the gate terminals, the drain currents of M1 and M2 vary accordingly. However, when identical inputs are applied, both MOSFETs conduct the same current. This configuration defines a common-mode input voltage differential amplifier.

For optimal operation, MOSFETs must remain in the saturation region rather than entering the triode region. The circuit’s functionality is assessed through DC analysis, transient analysis, and AC analysis (frequency response evaluation).

---

## Circuit-1: Differential Amplifier with Resistor Biasing


### Required Components
- **MOSFETs:** M1, M2, M3
- **Resistors:** Rss, Rd
- **Voltage Sources:** VDD, Input signals (Vicm)

### Design Approach
1. Construct a differential amplifier using MOSFETs M1 and M2.
2. Insert a resistor (Rss) at the shared source terminal to establish bias current.
3. Calculate the tail current (Iss) based on the given power (P) and supply voltage (VDD).
4. Evaluate the individual drain currents (Id1 and Id2) under balanced conditions.
5. Select appropriate values for Rss and Rd to achieve the desired gain and output voltage swing.
6. Optimize the width (W) and length (L) of M1 and M2 for enhanced performance.
   
## Derived values: L = 180nm, W = 108.5µm
![image](https://github.com/user-attachments/assets/4c2bdfa1-9667-44e4-b940-acae4ece9962)


### DC Analysis
![image](https://github.com/user-attachments/assets/9d08e8bd-059d-40d9-9062-d6766cac6ebf)

- Select DC operating point analysis in the simulation settings.
- Execute the simulation to determine drain current and output voltage values.
- The results confirm Vout as anticipated, with Id1 equaling Id2, ensuring balanced operation.

### Transient Analysis
![image](https://github.com/user-attachments/assets/e7158a4f-4182-4bf8-8dbf-dd1caa11f3ad)

- Configure transient analysis with a total run time of 5ms.
- Observe the amplifier’s time-domain response.

### AC Analysis
![image](https://github.com/user-attachments/assets/3430239e-6ec7-4473-bdf0-b4b0314643d0)

- Conduct AC frequency response analysis to evaluate gain and bandwidth.

---

## Circuit-2: Differential Amplifier with Current Source Biasing
![image](https://github.com/user-attachments/assets/858856d4-6a44-472e-8f6a-0e69b1a595fe)

### Modification
- Replace resistor Rss with a current source (1mA) to enhance stability.

### DC Analysis
![image](https://github.com/user-attachments/assets/28ed268a-4c55-428a-a8df-cc2a117aef80)

- Perform DC operating point analysis and verify steady bias conditions.

### Transient Analysis
![image](https://github.com/user-attachments/assets/cc215f31-0408-4c2c-a2a6-541b417c2f27)

- Apply a 180-degree phase shift to one MOSFET while keeping the other at 0 degrees.
- Assign an AC amplitude of 1 to one input while keeping the other at 0 (or -1).
- Execute the simulation and observe the improved transient response.

### AC Analysis
![image](https://github.com/user-attachments/assets/83cf0e82-bf8d-4b41-9618-9c9f9c729812)

- Carry out frequency response analysis to evaluate gain and bandwidth.

---

## Circuit-3: Differential Amplifier with MOSFET-Based Current Source
![image](https://github.com/user-attachments/assets/48075744-48ff-4082-a1fb-5f4ac8fa8571)

### Modification
- Replace the current source with a MOSFET-based active current source.
- **Given parameters:** Vp = 0.4V, Vt = 0.36V, resulting in a gate voltage of 0.76V.
- Adjust the W/L ratio of the new MOSFET for optimal performance.

### DC Analysis
![image](https://github.com/user-attachments/assets/18b05980-320b-42bd-bbe4-6ec316b5f523)

- Execute DC analysis to validate effective tail current regulation.

### Transient Analysis
![image](https://github.com/user-attachments/assets/66001a99-3e33-42f1-a1fa-30fea466a896)

- Assign an AC amplitude of 1 to one MOSFET while keeping the other at 0.
- Run the simulation and assess the improved transient behavior.

### AC Analysis
![image](https://github.com/user-attachments/assets/3bd35ad2-4021-428a-b66a-062db232f204)

- Examine gain and bandwidth characteristics.


## Results
### Circuit-1 (Resistor-Biased Design)
- DC analysis confirms MOSFETs operate in saturation, with equal drain currents for identical inputs.
- Transient response indicates proper differential operation.
- AC analysis reveals moderate gain and limited common-mode rejection.

### Circuit-2 (Current Source Biasing)
- Substituting the resistor with a current source enhances bias stability.
- The transient response exhibits improved symmetry and stability.
- AC analysis demonstrates increased gain and bandwidth compared to Circuit-1.

### Circuit-3 (MOSFET-Based Current Source)
- DC analysis confirms that the MOSFET-based current source effectively regulates tail current.
- Transient response is more precise and stable.
- AC analysis shows higher gain and superior frequency response.
- DC sweep verifies expected output variations corresponding to input changes.

---

## Conclusions
1. The tail current source plays a critical role in determining amplifier gain and stability.
2. The resistor-based configuration has lower gain and poor common-mode rejection.
3. A current source bias improves operational stability and differential performance.
4. A MOSFET-based current source offers superior gain, stability, and frequency response, making it the most effective design choice.
