<h1 align="center">Analog CMOS IC Design and Simulation Using Electric VLSI Tool 🔌</h1>

## 📌 Overview

<div align="justify">

This repository contains the design, layout, and simulation fundamental CMOS analog chips using the Electric VLSI EDA Tool and LTspice. The project focuses on essential CMOS building blocks commonly used in analog and digital IC design, including transistor-level schematic creation, layout implementation, and SPICE-based simulation.
</div>

## 🚀 Tools Used
<ul>
  <li><a href="https://staticfreesoft.com/productsFree.html">Electric VLSI EDA Tool (electricBinaryFull-9.08)</a></li>
  <li><a href="https://adoptium.net/temurin/releases/">Eclipse Temurin</a></li>
  <li><a href="https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html">LTspice</a></li>
</ul>

## 🔧 CMOS Analog Circuit Projects
<ul>
  <li>PMOS Transistor</li>
  <li>NMOS Transistor</li>
  <li>CMOS Inverter</li>
  <li>Common Source Amplifier</li>
  <li>Common Drain Amplifier</li>
  <li>Ring Oscillator</li>
</ul>

<p>Each project may include:</p>
<ul>
  <li>Schematic designs</li>
  <li>IC layouts</li>
  <li>SPICE netlists</li>
  <li>Simulation files</li>
  <li>Waveform outputs</li>
</ul>

## 🔗 Circuit Layouts & Netlists

### **[PMOS Transistor](https://github.com/ejramirez525/Analog-Integrated-Circuit-Design/tree/main/pmos)**

<div align="center">
  <img src="pmos\pmos-design.png" alt="PMOS IC Design" width="65%">
  <p><em>Fig. 1 PMOS Schematic and Layout</em></p>
</div>

* **DC Sweep Analysis** </br>
    In LTspice, open the generated netlist (`pmos/pmos.spi`) and plot the following traces: <br>
    * Id(Mpmos_1) upper pane</br>
    * Is(Mpmos_1) lower pane
    ```
    vs s 0 DC 0
    vb b 0 DC 0
    vg g 0 DC 0
    vd d 0 DC 0
    .dc vd 0 -5 -1m vg 0 -5 -1
    .include "C:\C5_models.txt"
    ```

---

### **[NMOS Transistor](https://github.com/ejramirez525/Analog-Integrated-Circuit-Design/tree/main/nmos)**

<div align="center">
  <img src="nmos\nmos-design.png" alt="NMOS IC Design" width="65%">
  <p><em>Fig. 2 NMOS Schematic and Layout</em></p>
</div>

* **DC Sweep Analysis** </br>
    In LTspice, open the generated netlist (`nmos/nmos.spi`) and plot the following traces: <br>
    * Id(Mnmos_0) upper pane</br>
    * Is(Mnmos_0) lower pane
    ```
    vs s 0 DC 0
    vb b 0 DC 0
    vg g 0 DC 0
    vd d 0 DC 0
    .dc vd 0 5 1m vg 0 5 1
    .include "C:\C5_models.txt"
    ```

---


### **[CMOS Inverter](https://github.com/ejramirez525/Analog-Integrated-Circuit-Design/tree/main/cmos-inverter)**

<div align="center">
  <img src="cmos-inverter\cmos-inverter-design.png" alt="CMOS Inverter IC Design" width="65%">
  <p><em>Fig. 3 CMOS Inverter Schematic and Layout</em></p>
</div>

* **DC Sweep Analysis** </br>
    In LTspice, open the generated netlist (`cmos-inverter/cmos-inverter-dc.spi`) and plot the following traces: <br>
    * V(vin) upper pane</br>
    * V(vout) lower pane
    ```
    vdd vdd 0 DC 5
    vgnd gnd 0 DC 0
    vin vin 0 pulse (0 5 0 1n 1n 20n)
    .include "C:\C5_models.txt"
    .dc vin 0 5 1m
    ```

* **Transient Analysis** </br>
    In LTspice, open the generated netlist (`cmos-inverter/cmos-inverter-tran.spi`) and plot the following traces: <br>
    * V(vin) upper pane</br>
    * V(vout) lower pane
    ```
    vdd vdd 0 DC 5
    vgnd gnd 0 DC 0
    vin vin 0 pulse (0 5 0 1n 1n 10n 20n)
    .include "C:\C5_models.txt"
    .tran 1n 100n
    ```

---

### **[Common Source Amplifier](https://github.com/ejramirez525/Analog-Integrated-Circuit-Design/tree/main/common-source-amplifier)**

<div align="center">
  <img src="common-source-amplifier\common-source-amp-design.png" alt="Common Source Amplifier IC Design" width="65%">
  <p><em>Fig. 4 Common Source Amplifier Schematic and Layout</em></p>
</div>

* **DC Analysis** </br>
    In LTspice, open the generated netlist (`common-source-amplifier\common-source-amp-dc.spi`) and plot both traces: <br>
    * V(vin)</br>
    * V(vout)
    ```
    vdd vdd 0 DC 5
    vin vin 0 dc 5
    .dc vin 0 5 .1
    .include "C:\C5_models.txt"
    ```

* **Transient Analysis** </br>
    In LTspice, open the generated netlist (`common-source-amplifier\common-source-amp-tran.spi`) and plot the following traces: <br>
    * V(vin) upper pane</br>
    * V(vout) lower pane
    ```
    vdd vdd 0 DC 5
    vin vin 0 sin(0.9 0.005 1k 0 0 0 50)
    .tran 0 5m
    .include "C:\C5_models.txt"
    ```

* **AC Analysis** </br>
    In LTspice, open the generated netlist (`common-source-amplifier\common-source-amp-ac.spi`) and plot the following traces: <br>
    * V(vin) upper pane</br>
    * V(vout) lower pane
    ```
    vdd vdd 0 DC 5
    vin vin 0 DC 0.9 AC 1
    .ac dec 100 100 10g
    .include "C:\C5_models.txt"
    ```

---

### **[Common Drain Amplifier](https://github.com/ejramirez525/Analog-Integrated-Circuit-Design/tree/main/common-drain-amplifier)**

<div align="center">
  <img src="common-drain-amplifier\common-drain-amplifier-design.png" alt="Common Source Amplifier IC Design" width="65%">
  <p><em>Fig. 5 Common Drain Amplifier Schematic and Layout</em></p>
</div>

* **DC Analysis** </br>
    In LTspice, open the generated netlist (`common-drain-amplifier\common-drain-amp-dc.spi`) and plot both traces: <br>
    * V(vin)</br>
    * V(vout)
    ```
    vdd vdd 0 DC 5
    vb vb 0 DC 1
    vin vin 0 dc 5
    .dc vin 0 5 .1
    .include "C:\C5_models.txt"
    ```

* **Transient Analysis** </br>
    In LTspice, open the generated netlist (`common-drain-amplifier\common-drain-amp-tran.spi`) and plot the following traces: <br>
    * V(vin) upper pane</br>
    * V(vout) lower pane
    ```
    vdd vdd 0 DC 5
    vb vb 0 DC 1
    vin vin 0 sin(4 1 1k 0 0 0 50)
    .tran 0 5m
    .include "C:\C5_models.txt"
    ```

* **AC Analysis** </br>
    In LTspice, open the generated netlist (`common-drain-amplifier\common-drain-amp-ac.spi`) and plot the following traces: <br>
    * V(vin) upper pane</br>
    * V(vout) lower pane
    ```
    vdd vdd 0 DC 5
    vb vb 0 DC 1
    vin vin 0 DC 4 AC 1 SIN(4 1 1k 0 0 0 50)
    .ac dec 100 100 10g
    .include "C:\C5_models.txt"
    ```

---

### **[Three Stage Oscillator](https://github.com/ejramirez525/Analog-Integrated-Circuit-Design/tree/main/ring-oscillator)**

<div align="center">
  <img src="ring-oscillator\ring-oscillator-design.png" alt="Ring Oscillator IC Design" width="65%">
  <p><em>Fig. 6 Common Drain Amplifier Schematic and Layout</em></p>
</div>

* **Transient Analysis** </br>
    In LTspice, open the generated netlist (`ring-oscillator\ring-oscillator.spi`) and plot the following trace: <br>
    * V(osc_out)</br>

    ```
    vdd vdd 0 DC 5
    .tran 0 30n
    .include "C:\C5_models.txt"
    ```
    ***Note:** Before running the SPICE simulation, all SPICE code in the CMOS inverter schematic and layout should be `removed` or converted into `*` comments.*
---