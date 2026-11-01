# DESIGN CALCULATIONS

## 1. LED Current-Limiting Resistor Calculation

A 5 mm white LED is used as the light source for the LDR sensor module. A current-limiting resistor is connected in series with the LED to prevent excessive current and protect it from damage.

**Given Parameters:**

| Parameter                                |             Value |
| ---------------------------------------- | ----------------: |
| Supply Voltage (\(V_{CC}\))              |               5 V |
| LED Forward Voltage ((V_F))              |  Approximately 3 V|
| Selected LED Operating Current (\(I_F\)) |             20 mA |

The required series resistance is calculated using Ohm's law:

$$
R = \frac{V_{CC} - V_F}{I_F}
$$

Substituting the values:

$$
R = \frac{5 - 3}{20\times10^{-3}}
$$

$$
R = 100\ \Omega
$$

A standard resistor value of 150 Ω can be selected for an operating current close to 20 mA.

Alternatively, a 330 Ω resistor can be used for a lower LED current, providing a more conservative operating condition.

For a 330 Ω resistor:

$$
I_F = \frac{5-3}{330}
$$

$$
\boxed{I_F \approx 6.06\text{ mA}}
$$

Selected Component: 330 Ω current-limiting resistor.

---

## 2. MOSFET Gate-Series Resistor Calculation

The IRLZ44N N-channel MOSFET is used as a switching device in the visitor-counting system. A 1 kΩ resistor is connected between the digital output (DO) of the LDR sensor module and the MOSFET gate.

This resistor limits the transient current flowing into the MOSFET gate during switching.

**Given Parameters:**

| Parameter                          | Value |
| ---------------------------------- | ----: |
| Sensor Output Voltage (\(V_{DO}\)) |   5 V |
| Gate-Series Resistance (\(R_G\))   |  1 kΩ |

Assuming an initial gate voltage of approximately 0 V, the theoretical initial gate current is:

$$
I_G = \frac{V_{DO}}{R_G}
$$

Substituting:

$$
I_G = \frac{5}{1000}
$$

$$
\boxed{I_G = 5\text{ mA}}
$$

The initial current decreases as the MOSFET gate charges. Under steady-state conditions, the gate draws negligible DC current, apart from leakage.

The selected 1 kΩ resistor is suitable for the low-frequency switching operation of the proposed visitor-counting system.

---

## 3. MOSFET Drain Current Calculation

The IRLZ44N N-channel MOSFET is configured as a low-side switch to control the 5 V buzzer.

When the MOSFET turns ON, current flows from the positive supply through the buzzer and the MOSFET drain-source path to ground.

### Given Parameters

| Parameter                        |    Value |
| -------------------------------- | -------: |
| Supply Voltage (\(V_{CC}\))      |      5 V |
| Measured Buzzer Resistance       | 1.666 kΩ |
| Gate-Series Resistance (\(R_G\)) |     1 kΩ |
| Measured Drain Current (\(I_D\)) |     3 mA |

### Experimental Drain Current Measurement

The drain current was measured experimentally using a digital multimeter connected in series with the buzzer while the circuit was operating at 5 V.

The measured current was:

$$
\boxed{I_D = 3\text{ mA}}
$$

Since the buzzer and MOSFET are connected in series in the load-current path, the measured buzzer current corresponds to the MOSFET drain current.

### MOSFET Power Dissipation

The conduction power dissipated by the MOSFET can be estimated using:

$$
P_D = I_D^2 \times R_{DS(on)}
$$

For the calculation, the IRLZ44N datasheet ON-state resistance value of 0.025 Ω is used.

Substituting:

$$
P_D = (0.003)^2 \times 0.025
$$

$$
\boxed{P_D = 0.225\ \mu W}
$$

### Experimental Results

| Parameter                           |    Value |
| ----------------------------------- | -------: |
| Operating Voltage                   |      5 V |
| Measured Drain Current              |     3 mA |
| \(R_{DS(on)}\) Used for Calculation |  0.025 Ω |
| Estimated MOSFET Conduction Loss    | 0.225 µW |

**Observation:** The IRLZ44N successfully operates as a low-side switching device, controlling the buzzer with an experimentally measured drain current of approximately 3 mA. The estimated conduction power loss is very low under the stated operating conditions.
