# Experiment-3: MOS Differential Amplifier Design and Analysis

## Objective
To design and evaluate a MOS differential amplifier circuit based on given parameters, performing DC analysis, transient analysis, and frequency response assessment to extract key performance characteristics.

---

## Given Parameters
- **Supply Voltage (VDD):** 2.2V
- **Maximum Power Consumption (P):** 2mW
- **Common-Mode Input Voltage (Vicm):** 1.2V
- **Common-Mode Output Voltage (Vocm):** 1.25V
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
   - **Derived values:** L = 190nm, W = 6.7877µm

### DC Analysis
- Select DC operating point analysis in the simulation settings.
- Execute the simulation to determine drain current and output voltage values.
- The results confirm Vout as anticipated, with Id1 equaling Id2, ensuring balanced operation.

### Transient Analysis
- Configure transient analysis with a total run time of 5ms.
- Observe the amplifier’s time-domain response.

### AC Analysis
- Conduct AC frequency response analysis to evaluate gain and bandwidth.

---

## Circuit-2: Differential Amplifier with Current Source Biasing
### Modification
- Replace resistor Rss with a current source (1mA) to enhance stability.

### DC Analysis
- Perform DC operating point analysis and verify steady bias conditions.

### Transient Analysis
- Apply a 180-degree phase shift to one MOSFET while keeping the other at 0 degrees.
- Assign an AC amplitude of 1 to one input while keeping the other at 0 (or -1).
- Execute the simulation and observe the improved transient response.

### AC Analysis
- Carry out frequency response analysis to evaluate gain and bandwidth.

---

## Circuit-3: Differential Amplifier with MOSFET-Based Current Source
### Modification
- Replace the current source with a MOSFET-based active current source.
- **Given parameters:** Vp = 0.4V, Vt = 0.36V, resulting in a gate voltage of 0.76V.
- Adjust the W/L ratio of the new MOSFET for optimal performance.

### DC Analysis
- Execute DC analysis to validate effective tail current regulation.

### Transient Analysis
- Assign an AC amplitude of 1 to one MOSFET while keeping the other at 0.
- Run the simulation and assess the improved transient behavior.

### AC Analysis
- Examine gain and bandwidth characteristics.

### Gain Calculation
\[
\text{Gain} = \frac{V_{out}}{V_{in}} = \frac{1.32}{1.25} = 1.056
\]

---

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
