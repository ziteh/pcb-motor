# PCB Motor

AF-PMSM (axial flux permanent magnet synchronous machine) PCB stator, inspired by the [sabanekko3/pcb_stator_v2](https://github.com/sabanekko3/pcb_stator_v2) and [CarlBugeja/PCB-Motor-v4](https://github.com/CarlBugeja/PCB-Motor-v4).

## Note

### Slot/Pole

In the design of a PMSM, selecting the slot/pole topology is the first step [5].

The Star of Slot (SOS) method is commonly used for this purpose.

- Pole: The number of permanent magnets.
- Slot: The number of coil slots.

The slot-to-pole relationship can be classified into:

- Integer-slot
- Fractional-slot

For a three-phase motor, the relationship can be analyzed as follows:

$$
Q=\frac{N_{s}}{3\cdot 2p}
$$

where:
- $Q$ is the slot per pole per phase.
- $N_s$ is the total number of slots.
- $p$ is the number of pole pairs.

### Topology

Based on [1], the winding layout can be categorized into the following types:
1. Concentric
2. Parallel
3. Radial [2]
4. Arc
5. Unequal width parallel

The design in [1] features a 144-slot , 16-pole configuration with 3 slots per pole per phase on a double-layer PCB. The PCB has a thickness of 1mm, an air gap of 1mm, and a copper thickness of 70μm.

According to the findings, radial and concentric windings exhibit the highest torque and induced phase voltage. However, among these, the concentric winding has the highest losses and THD (Total Harmonic Distortion). The radial winding has the lowest THD, making it suitable for high-precision applications. The parallel winding has the lowest resistance, whereas the unequal width parallel winding reduces phase resistance by 17% compared to the standard parallel winding while maintaining the same induced phase voltage and output torque.

The study in [3], based on the results of [1], selected the radial winding layout for PCB motor design. However, an axial unequal-width winding design was adopted. The primary advantage of using unequal width traces is that the larger copper cross-sectional area results in lower phase resistance compared to equal-width traces. Additionally, increasing the total copper area helps reduce thermal stress by providing lower thermal resistance.

The motor specifications are as follows:
- Pole count: 20
- PCB thickness: 2mm
- PCB layers: 6
- Copper thickness: 140μm
- Air gap: 1mm

### Rotor

For permanent magnet rotors, the Halbach array can be considered.

## Ref

1. [Comparison of PCB winding topologies for axial-flux permanent magnet synchronous machines](https://doi.org/10.1049/iet-epa.2020.0622)
2. [Comparative analysis of wave winding topologies and performance characteristics in ultra-thin printed circuit board axial-flux permanent magnet machine](https://doi.org/10.1049/iet-epa.2018.5417)
3. [Mechanical and Thermal Design of an Optimized PCB Motor for an Integrated Motor Drive System With GaNFETs](https://doi.org/10.1109/TEC.2022.3213896)
4. [Axial-flux permanent-magnet machine modeling, design, simulation and analysis](https://www.researchgate.net/publication/228847506_Axial-flux_permanent-magnet_machine_modeling_design_simulation_and_analysis)
5. [Analysis of slot-pole combination of fractional-slots PMSM for embedded applications](https://doi.org/10.1109/ACEMP.2011.6490669)
6. [Analytical Study and Comparison of Electromagnetic Characteristics of 8-Pole 9-Slot and 8-Pole 12-Slot Permanent Magnet Synchronous Machines Considering Rotor Eccentricity](https://doi.org/10.3390/electronics10162036)
7. [Design and Testing of PMSM for Aerospace EMA Applications](http://dx.doi.org/10.1109/IECON.2018.8591318)
8. [プリント基板コイル（PCBステータ）を使ってモーターを作る会　その１ - さばと根っこな製作記](https://sabanekko2.hatenablog.com/entry/2023/03/06/130205)
