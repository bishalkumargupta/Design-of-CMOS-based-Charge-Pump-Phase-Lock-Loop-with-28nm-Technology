# Design of CMOS based Charge Pump Phase Lock Loop with 28nm Technology

## Table of Contents

- Abstract 
- Introduction
- Expected waveform
- Circuit implementation of PFD block 
- Circuit implementation of CP + LPF block
- Circuit implementation of VCO block
- Simulation Result
- Conclusion
- Author
- Acknowledgements
- References
## Abstract
CMOS based Chare Pump Phase Locked Loop is being Simulated and recorded on 28nm technology. Phase Frequency Detector, charge pump with LPF and Voltage controlled oscillator is being implemented ,cascaded and recorded in this work. Phase frequency Detector(PFD) plays a most important role in a PLL. PFD decides the performance and accuracy of a PLL. Charge pump is also a major block for a PLL which translate frequency and phase into voltages as DC codes with the help of LPF used to tune VCO. Tuned VCO acts as local oscillator and hence generates frequecy proportionally. PLL act as clock generator and is a non-linear feedback system that tracks the phase of the input signal and minimise the phase error at the local oscillator. PLL has a wide range of application in modern and conventional electronics and communication technologies, such as frequency synthesizers, FM and AM coherent demodulation analysis and more.
## Introduction

 - Phase Lock Loop (PLL)  is the most important block of any clocking system of circuit design and comprise essential applications which includes synchronization of cock in communication system, RF applications , wireless devices, day to day modern electronic equipments. PLLs consists of many blocks where the major ones are Phase Frequency Detector(PFD), Charge Pump(CP), Low Pass Filter(LPF), Voltage Controlled Oscillator(VCO) and Frequency Divider. PFD is the major block of a frequency synthesiser.</br.
 - A PFD compares the two input signals, i.e. reference input and feedback input as shown in Fig. 1. Depending upon the phase difference, PFD generates either UP signal or DOWN signal. This signal drives CP which produces a current pulse with corresponding duty ratio.
 - CP circuit consists of a Pull up and Pull-Down network. Charge pump maintain constant output with a varying voltage which later is used to tune the VCO. In Fig. (3) Inputs “UP” and “Down” control the Switches S1and S2 respectively. A pulse of width dT Up turns S1on for dT sec, availing I1 to charge C1. Vout goes up by dT*I1/C1. With same phenomena, Down pulse gives a drop in Vout. If Up and Down are provided simultaneously, I1flows through S1and S2 as I2, resulting into Vout unchanged.</br>
 - The voltage controlled oscillator performance governs many aspects of the performance of the whole phase locked loop or frequency synthesizer. Accordingly careful design is necessary.Like any oscillator, a VCO may be considered as an amplifier and a feedback loop. For the circuit to oscillate the total phase shift around the loop must be 360° and the gain must be unity. In this way signals are fed back round the loop so that they are additive and as a result, any small disturbance in the loop is fed back and builds up.

<p align="center">
<img src="https://user-images.githubusercontent.com/86653033/155883134-05e3eee9-1cd6-4960-bb69-840a6aac6893.png">
</p>
<p align="center">
Fig 1. Block diagram of basic charge pump PLL
</p>

## Reference Circuit Design

<p align="center">
<img src="https://user-images.githubusercontent.com/86653033/155875626-d3c9baf2-c100-4356-9b3e-5915b943f3ab.png">
</p>
<p align="center">
Fig 2. (a) Cascaded PFD/CP/LPF circuit diagram (b) Transmission gate based DFlipFlop
</p></br>
<p align="center">
<img src="https://user-images.githubusercontent.com/86653033/155885824-eb4a0162-1e1c-47dd-b421-b3b4e6995ca6.png">
</p>
<p align="center">
Simple Charge Pump PLL
</p></br>

## Expected waveform
<p align="center">
<img src ="https://user-images.githubusercontent.com/86653033/155875851-5accd622-1326-48ef-a9a8-ed6f0b9c7db1.png">
  </p>
  <p align="center">
  Waveform of cascaded PFD and CP
  </p>

## Circuit implementation of PFD block.
This is the CMOS circuit implementation of AND Gate
<p align="center">
 <img src ="https://user-images.githubusercontent.com/86653033/155886400-31b7f9bd-24e5-4038-956c-11fe1b0cf324.png">
  </p></br>
This is the CMOS circuit implementation of NOR Gate
<p align="center">
 <img src ="https://user-images.githubusercontent.com/86653033/155886484-c246b868-9b72-4324-ad08-f874ce78ef8d.png">
  </p>
This the D latch(modified) implementation where NOR gate is being instantiated after symbolising the design in the tool</br>
<p align="center">
<img src ="https://user-images.githubusercontent.com/86653033/155876934-b2091c79-58f7-4a90-a96c-a6028b1dbbe7.png">
  </p></br>
This the PFD block which is implemented using D Latch and And Gate for providing Reset (R) control and the UP output is denoted by "QA" and DOWN is represented by "QB". And further symbol of PFD is made.</br> CLKA represents the Reference clock</br> CLKB represens the Feedback signal </br>

 <p align="center">
<img src ="https://user-images.githubusercontent.com/86653033/155877443-36e258a4-d65e-4ce1-8f64-b23a9a946abd.png">
</p>

## Circuit implementation of CP + LPF block.
</br>This is the circuit implementation of Charge Pump whis is further connected to LPF block</br>
<p align="center">
<img src ="https://user-images.githubusercontent.com/86653033/155877668-0f029bb0-786a-4fd6-a104-38a2dcd56c71.png">
</p>

</br>This is the cascaded implementation of the PFD/CP/LPF combined</br>
<p align="center">
<img src ="https://user-images.githubusercontent.com/86653033/155877912-5ed679a1-8697-4ca4-8e7f-2ed804bb54b8.png">
</p></br>

## Circuit implementation of VCO block.
This is the circuit implementation of VCO block</br>
<p align="center">
<img src ="https://user-images.githubusercontent.com/86653033/155882151-acc8208a-9d18-4aea-8266-0aff391108ba.png">
</p></br>
This is the cascaded Block of VCO + CP + LPF + PFD blocks and the VCO output is being given to the PFD block as a feedback</br>

<p align="center">
<img src ="https://user-images.githubusercontent.com/86653033/155882463-f70fd252-fd61-4828-bb0b-ee06e97cf48b.png">
</p></br>




  
 
 


## Simulation Results
- Case1:- When Reference clock(CLKA) leads Feedback Clock(CLKB)</br>
<p align="center">
<img src ="https://user-images.githubusercontent.com/86653033/155878058-63e6187c-8019-433f-af11-beed874268b8.png">
</p></br>
- Case2:- When CLKA lags CLKB</br>
 </br><p align="center">
<img src ="https://user-images.githubusercontent.com/86653033/155878125-98fee578-135e-400f-a002-093a4ce1d658.png">
</p></br>
For the case1 the test bench for PFD block obtained is given here. similiarly the test bench for whole circuit was arranged
<p align="center">
<img src ="https://user-images.githubusercontent.com/86653033/155886700-286c2eac-4f59-4c3b-afe5-e70720e0d771.png">
</p></br>

Considering Case1 , when CP and LPF is being cascaded with the PFD block the simulation result is being pfovided</br>
</br><p align="center">
<img src ="https://user-images.githubusercontent.com/86653033/155884539-e1eec48f-3282-4c4c-8d16-817d6f0cc0a8.png">
</p></br>
Considering VCO the output of the CPLL is being shown</br>
<p align="center">
<img src ="https://user-images.githubusercontent.com/86653033/155882621-1227a6eb-c6c1-449d-bfcf-0d76f8c52a22.png">
</p></br>


## Conclusion

The repository presents the design and simulation of CMOS based 28nm Technoogy Charg Pump Phase Locked Loop(CPPLL) having a operating frequency of 500MHz with operating voltage be 1.5V where the schematic and the waveforms are being produced here. With suitable strength of MOSFETS, noise clean outputs are being ectracted.

## Author

Bishal Kumar Gupta, M.tech at Defence Institute of Advanced Technology-DRDO [in collaboration with NIELIT CALICUT] with specialization in VLSI and Embedded Systems, Department of Electronics Engineering.

## Acknowledgements

- [Kunal Ghosh, Co-founder, VSD Corp. Pvt Ltd.](https://www.linkedin.com/in/kunal-ghosh-vlsisystemdesign-com-28084836?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_contact_details%3B0xcWjpLDThSEo6S9UPO9Tw%3D%3D)
- Chinmay Panda, IIT Hyderabad
- [Synopsis Team/Company](synopsys.com/company/contact-synopsys/office-locations/india/about-synopsys-india.html)
- [IIT Hyderabad](https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/)
- Active and vibrant hackathon community

## References

[1] I. Galton, B. Razavi, J. Cowles and P. Kinget, "CMOS phase-locked
loops for frequency synthesis," 2010 IEEE International Solid-State
Circuits Conference - (ISSCC), 2010, pp. 521-521, doi:
10.1109/ISSCC.2010.5433853.</br>
[2] H. Dadhich, V. Maurya, K. Verma and S. Jaiswal, "Design and analysis
of different type of charge pump using CMOS technology," 2016
International Conference on Advances in Computing, Communications
and Informatics (ICACCI), 2016, pp. 294-298, doi:
10.1109/ICACCI.2016.7732062.</br>
[3] RF Microelectronics Textbook written by Behzad Razavi.</br>
[4] Won-Hyo Lee, Jun-Dong Cho and Sung-Dae Lee, "A high speed and
low power phase-frequency detector and charge-pump," Proceedings of
the ASP-DAC '99 Asia and South Pacific Design Automation
Conference 1999 (Cat. No.99EX198), 1999, pp. 269-272 vol.1, doi:
10.1109/ASPDAC.1999.760011.</br>

