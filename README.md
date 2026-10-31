# MOSFET-Based-Visitor-Counter
A hardware-efficient visitor counting system using LDR-based optical sensing, MOSFET switching, and digital logic for public-space monitoring.

# PROJECT_OVERVIEW
The system uses an LDR sensor module to detect interruptions in incident light. The resulting signal is processed by an electronic switching circuit, while a CD4026 counter drives a seven-segment display to indicate the count. The project demonstrates the practical application of discrete electronics, sensor interfacing, MOSFET switching, and digital logic in a people-counting prototype.

# OBJECTIVES 
  1. To detect and count objects passing through a monitored area using incident-light interruption.
  2. To design and implement a MOSFET-based switching circuit for electronic signal control.
  3. To integrate a buzzer as an audible alert to indicate visitor passage.

# COMPONETS REQUIRED 
  Component	Specification                                          
  1. Regulated DC power supply 5 V DC -  Powers the circuit assembly
  2. LDR sensor module	3-pin module: VCC, GND, DO - Detects the change in incident light 
  3. White LED	Light source for intruder detection - Fixed light source
  4. CD4026BE IC	Decade counter with seven-segment decoder - The CD4026 is a CMOS decade counter and 7-segment display                                                                    driver combined into a single 16-pin package. Is used to count                                                               the total visitors crossing.
     
  5. 74LS04 IC	Hex inverter IC -                                                Since I used common Anode display, I had to                                                                                  invert the logic to display using IC4046BE                                                                                   counter which uses Common cathode encoder.                                                                                   This IC is not required if using Common                                                                                      Cathode display
     
  6. IRLZ44N MOSFET	N-channel power MOSFET -                                   Electronic switching
    
  7. Seven-segment display(CC or CA type) -                                  Displays the count
    
  8. Buzzer	5 V compatible -                                  Audible alert
    
  14. Resistor	330 Ω, current-limiting resistor	
  15. Resistor	1 kΩ, MOSFET gate series resistor	
  16. Breadboard - For circuit assembly	
# Potential Applications
1. Visitor-counting demonstrations
2. Entrance monitoring prototypes
3. Library and laboratory entry monitoring
4. Public-space people-counting concepts
5. Digital electronics laboratory experiments

# Future Improvements
1. Implement separate entry and exit detection.
2. Add occupancy tracking by accounting for entries and exits.
3. Integrate a microcontroller for data logging.
4. Add wireless monitoring and notifications.
5. Improve sensor accuracy and noise immunity.
6. Design a compact printed circuit board (PCB).





