# Exp-2
# EXPERIMENT--3
A differential amplifier amplifies the difference between two input signals while rejecting common-mode noise, making it a crucial component in precision applications such as measurement and communications.  It is made up of two transistors or an operational amplifier, with resistors to control the gain.  Resistor ratios determine differential gain (Ad), whereas the common-mode rejection ratio (CMRR) reveals the amplifier's noise suppression ability.  A high CMRR is ideal since it minimizes interference from external sources.  Signal conditioning, sensor amplification, and audio processing are all practical applications that require reliable differential signal amplification.
## Question:- 
Design the defferntial amplifier for the given parameters and do DC, AC and Transisent analysis by replacing the Rss with current source and current source, Rd with MOSFET.
### Given Parameters
* Vdd=3.3v
* p<=3mw
* Vincm=1.72v
* Vocm=1.81v
* Vp=0.7v

### Extracting parameters from the given values are:-
1. Iss=P/Vdd
=3*10^-3/3.3k
=0.90mA
2. Id=Iss/2=0.45mA
3. Rd=Vdd-Vocm/Id=3.3kohm
4. Rss=Vp/Iss=777ohm
## Circuit Diagram
![Screenshot 2025-03-12 204043](https://github.com/user-attachments/assets/bbefc3b0-0895-4a32-bf59-9fb4e8a55e63)

## Procedure
* Create a circuit schematic in LTSpice using the instructions provided.
 * Provide extracted values for each component.
 * To obtain an accurate output, change the widths of both transistors.
 *  Attach the library file before running the simulation.
 * Run DC, AC, and transient analyses and compare the simulation and computed values.
 * Check the waveform and bandwidth.
 *  Replace Rss with the current source and do a DC, AC, and transient analysis.
 *  Replace MOSFET with MOSFET and repeat the DC, AC, and transient study.
 *  Replace both Rd with MOSFETs and set the Vb value and width of the transistor. Perform the same DC, AC, and transient analysis.

### DC Analysis
To Perform DC Analysis  In the edit simulation, choose DC operation point.

 Set the right Length=180nm and Width=7.8um values to acquire the desired ID
![Screenshot 2025-03-12 204548](https://github.com/user-attachments/assets/1ebee6b5-a542-48d6-92bd-cf8f7a936ac6)

### AC Analysis
Procedure for AC Analysis:
* Click the run and choose the AC Analysis mode.
* Right-click on V1 and select Small Signal AC Analysis. Set Amplitude to 1.
* Set the sweep type to Decade, the number of points per decade to 20, and the start and stop frequencies to 0.1Hz and 1THZ, respectively.
* Click on ok
![AC output](https://github.com/user-attachments/assets/2504d1db-f47c-4997-8ec1-ccd072471917)

### Transient analysis
Transient analysis was used to track how the output voltage waveform changed over time in response to the applied AC input signal.  This analysis is then used to determine how amplifiers affect real-time behavior, including signal amplification and distortions.  . The tran 5 m command will run the simulation for 5 milliseconds and provide a real-time description of the circuit's activities.
![transient output](https://github.com/user-attachments/assets/a2e796a2-f1fb-443f-9aa5-924ab7f3792a)

## Replaced Rss with a Current Source(0.90mA)
![Screenshot 2025-03-12 210135](https://github.com/user-attachments/assets/00785ce3-d3d9-4737-9213-5a57ae957918)

### DC Analysis
![Screenshot 2025-03-12 210206](https://github.com/user-attachments/assets/b7524292-2cc6-46f2-be15-f5db8ad0ae94)
### AC Analysis

![AC output](https://github.com/user-attachments/assets/1da3489d-1c31-44d4-a827-8bfe78eb1b3b)

### Transient Analysis

![image](https://github.com/user-attachments/assets/90c50d5c-6473-4ca1-b9fb-c29e652534e8)


## Replaced Current source with MOSFET(Length=180nm, Width=17.8um) 
![Screenshot 2025-03-12 212851](https://github.com/user-attachments/assets/0128b101-924e-4494-a474-f0c93a6c8a69)

### DC Analysis
![Screenshot 2025-03-12 212138](https://github.com/user-attachments/assets/ff9e1b62-5f39-4e97-9607-9c2f5898d446)

### AC Analysis

![image](https://github.com/user-attachments/assets/a09cce3b-26ce-4994-9553-d9c959e6cee8)

### Transient Analysis

![Mc Transient op](https://github.com/user-attachments/assets/ab730dce-7720-4276-abfa-5adb0605921a)

## Replaced Rd with PMOS MOSFET (Length=180nm & Width=3.65um)
![Screenshot 2025-03-12 214042](https://github.com/user-attachments/assets/294d6301-61a0-4301-b849-6d7cfe6d19db)

### DC Analysis
![Screenshot 2025-03-12 213838](https://github.com/user-attachments/assets/b79db59e-cbdc-4465-bf30-c2181e259b0b)

### AC Analysis

![image](https://github.com/user-attachments/assets/6bf6a735-e820-4486-9255-39d48a86d342)

### Transient Analysis 

![image](https://github.com/user-attachments/assets/c2853dff-480b-4b8c-9350-c3499972d683)

# Inference 
### The Id depends on Vb or Vincm value.
 * The common-mode input voltage (Vincm) influences the drain current (𝐼d) in each NMOS transistor (M1, M2).
   As Vincm  increases, the matching NMOS transistor's Id lowers, resulting in a greater output voltage ( Vout​).
 * If Vincm increases that side Id will decreases and vout will increase.
### Iss always in constant.
* The current source created by M3 ensures that the total back current remains constant, which aids in the differential operation.
 This is critical for achieving a consistent differential gain.
### High CMRR value indicates effective common mode noise rejection.
* A high CMRR ensures effective rejection of common-mode noise (unwanted signals that affect both inputs equally).
* This is critical in applications such as sensor signal processing and operational amplifiers, which amplify differential signals while rejecting noise.

* Resistor mismatch decreases gain stability and diminishes CMRR.
* Biasing guarantees that the amplifier acts symmetrically.

# Final Conclusion
* This circuit functions as a differential amplifier and is susceptible to common-mode changes.
* The CMRR is crucial for rejecting noise, and careful biasing guarantees adequate amplification.
* Mismatches in transistors or resistors can cause performance loss, lowering gain and stability.
