# current-mirror

A current mirror is an electronic circuit that takes a reference current and reproduces it at its output, creating a stable and reliable current source. It usually involves two or more transistors that are closely matched—one sets the reference current, and the others replicate it. These circuits are essential in analog design, especially for tasks like biasing, signal processing, and amplification. They are valued for their accuracy and ability to maintain consistent performance. Variants like the Wilson and cascode current mirrors improve functionality by reducing errors and increasing output resistance. These circuits are common in integrated circuits and play a key role in devices like amplifiers, voltage regulators, and differential pairs.
To put it simply, a current mirror "copies" a current from one part of the circuit to another, even if the output faces changing conditions. The current being duplicated can even be a varying signal. An ideal current mirror acts like a perfect current amplifier, reversing the direction of the current flow. Practically, they are used to provide steady bias currents, simulate realistic current sources, and serve as active loads in circuits, which helps address the limitation of ideal sources

        ![image](https://github.com/user-attachments/assets/fdb71dec-eb6b-4140-9b3e-6616de91f7b5)


        ![image](https://github.com/user-attachments/assets/e97aade9-92e1-4e07-aea8-6f905864c39d)


When it comes to current mirrors, there are three key aspects that define their performance:

1. **Transfer Ratio or Output Current Magnitude**: For a current amplifier, the transfer ratio measures how well the output replicates the reference current. In the case of a constant current source (CCS), it refers to the strength of the output current.
   
2. **AC Output Resistance**: This characteristic determines how stable the output current remains when the voltage across the mirror changes. A higher resistance means less variation and better performance.
   
3. **Minimum Voltage Drop**: For the current mirror to function correctly, the output transistor must stay in active mode. This requires a certain minimum voltage drop across the output part of the mirror. The range of voltages where the mirror operates as intended is called the *compliance range*, and the voltage that separates proper functioning from malfunctioning is the *compliance voltage*.

In addition to these primary specifications, there are secondary factors to consider, like temperature stability, which can also affect the performance of a current mirror.


> CASE 1 : To design and analysis current mirror circuit as active load in amplifier circuit for Av > -10V/V, Vdd=1.8V, P<1mW.

![image](https://github.com/user-attachments/assets/ac94931f-a324-463a-b4b3-c1af4b640343)


It=(Power/Vdd)

=(1m/1.8)

=0.5mA
Iref=Id=(Itotal/2)

=0.5m/2

=0.27mA

i. DC analysis:

![image](https://github.com/user-attachments/assets/794c1fd5-abc8-4f63-89a1-8c78d9da28f5)

![image](https://github.com/user-attachments/assets/8ee48e68-e607-446d-8f0c-37fd868ef476)

![image](https://github.com/user-attachments/assets/155b22c3-2b41-4fe2-bdf0-f065c6c8642e)



When analyzing the DC behavior of a current mirror circuit, the goal is to determine the reference current and assess how accurately it’s replicated at the output. In a simple BJT current mirror, the reference current is established using an external resistor. This current flows through a diode-connected transistor, creating a base-emitter voltage. Another identical transistor then mirrors this current. However, real-world imperfections, like mismatches between transistors, base currents, and the Early effect, can cause small deviations.

Similarly, in a MOSFET-based current mirror, the gate-source voltage controls the mirroring process. However, channel length modulation can impact accuracy. To counter these issues, advanced designs such as the Wilson and cascode current mirrors are employed. These designs improve precision by increasing output resistance and minimizing systematic errors.

In the specific circuit described:
- **MOSFET Length**: 180 nm  
- **Width of M3**: 101 µm  
- **Vout**: 1.162 V  

This circuit operates in the saturation region, meaning the condition \( V_{ds} > V_{gs} - V_{th} \) is satisfied.


ii. Transient Analysis:

![image](https://github.com/user-attachments/assets/b9cc4ad7-6c26-4e33-be80-0928dbd31f0b)

![image](https://github.com/user-attachments/assets/2ff346f6-9d6f-4e50-a689-374bc4bafff0)



Transient analysis of a current mirror focuses on how it reacts to time-varying signals and how quickly it stabilizes to replicate the reference current. When power is first applied, the transistors experience a brief settling period as the base-emitter or gate-source voltages adjust to generate the required current. During this phase, factors like junction capacitances and stray parasitics within the transistors play a role in the circuit's speed and stability.

In BJTs, delays caused by base charging can lead to minor overshoots or undershoots in the output current (\(I_{out}\)). On the other hand, in MOSFETs, the gate capacitance influences how quickly the circuit transitions to steady-state operation. To enhance transient performance, engineers often use techniques like adding compensation capacitors or incorporating active feedback circuits. These methods help reduce settling time and improve stability.

In the specific setup described:
- **Input Voltage**: 0.5 V  
- **Amplitude**: 1 mV  
- **Frequency**: 1 kHz  
- **Output Voltage**: 1.19 V  

The circuit operates in the saturation region, which satisfies the condition \( V_{ds} > V_{gs} - V_{th} \).

iii. AC analysis:



AC analysis of a current mirror focuses on its small-signal performance, particularly output impedance and frequency response. Ideally, the mirror’s output impedance should be high to ensure precise current replication. However, practical limitations like channel length modulation can lower this impedance. As the frequency increases, parasitic capacitances—such as gate-drain and drain-substrate capacitances—begin to introduce phase shifts and affect circuit stability. These issues limit the mirror’s bandwidth and accuracy. To address these challenges, advanced designs like cascode configurations or gain-boosted mirrors are used to enhance output impedance and reduce distortions caused by frequency changes.

When analyzing a 1:1 current mirror, the focus is on understanding how it responds to small input signal variations while maintaining its DC operating point. The primary goal is to assess how closely the output current matches the reference current and examine its frequency response and small-signal behavior. In a 1:1 configuration, both transistors are made identical so that the output current ideally mirrors the reference current. Small-signal characteristics, such as transconductance (\(g_m\)) and output conductance (\(g_{ds}\)), play key roles in determining how the circuit handles minor variations in the input signal.


![image](https://github.com/user-attachments/assets/ece7536b-86b6-469c-a1bd-7d0c8117f334)

![image](https://github.com/user-attachments/assets/12943ded-64df-42db-adac-05ff508179df)

gain = 29.45db

![image](https://github.com/user-attachments/assets/acd16c3e-d0e3-45dc-8071-e33601226eca)

3db = 26.45
