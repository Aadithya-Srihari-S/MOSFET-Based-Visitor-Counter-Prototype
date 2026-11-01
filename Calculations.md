**TO CALCULATE LED CURRENT AND RESISTOR REQUIRED TO LIMIT IT**


Given:
Supply voltage, VCC = 5 V
A standard 5mm white LED can withstand a current of 15mA. So we need a current limiting resistor of resistance

$$
R(in\,ohms) = 5V / 15mA ~= 330 ohms
$$

**GATE SERIES RESISTOR CALCULATION**

A 1 kΩ resistor is connected between the digital output (DO) of the LDR sensor module and the gate terminal of the IRLZ44N MOSFET.

Assuming a 5 V HIGH output from the sensor module, the theoretical initial gate current is:

$$
I_G = \frac{V_{DO}}{R_G}
$$

$$
I_G = \frac{5}{1000}
$$

$$
\boxed{I_G = 5\,mA}
$$

The resistor limits the transient gate-charging current and helps control the MOSFET switching transition. The selected 1 kΩ resistance is suitable for the low-frequency switching operation of the proposed visitor-counting system.

## 2. MOSFET Drain Current Calculation

The IRLZ44N N-channel MOSFET is used as a low-side switching device to control the 5 V buzzer.

### Given Parameters

| Parameter                                   |    Value |
| ------------------------------------------- | -------: |
| Supply Voltage (\(V_{CC}\))                 |      5 V |
| Buzzer Measured Resistance                  | 1.666 kΩ |
| Gate-Series Resistance (\(R_G\))            |     1 kΩ |
| Measured Drain Current (\(I_D\))            |     3 mA |
| MOSFET ON-State Resistance (\(R_{DS(on)}\)) |  0.025 Ω |

### Experimental Drain Current

The drain current was measured by connecting a digital multimeter in series with the buzzer while operating the circuit at 5 V.

The measured current was:

$$
\boxed{I_D=3\text{ mA}}
$$

### MOSFET Power Dissipation

The conduction power dissipated by the MOSFET is calculated using:

$$
P_D=I_D^2\times R_{DS(on)}
$$

Substituting:

$$
P_D=(0.003)^2\times0.025
$$

$$
\boxed{P_D=0.225\ \mu W}
$$

### Experimental Results

| Parameter                        |    Value |
| -------------------------------- | -------: |
| Operating Voltage                |      5 V |
| Measured Drain Current           |     3 mA |
| MOSFET ON-State Resistance Used  |  0.025 Ω |
| Calculated Conduction Power Loss | 0.225 µW |

**Observation:** The IRLZ44N operates as a low-side switch, controlling the buzzer with a measured drain current of approximately 3 mA. The calculated conduction loss is very low.


