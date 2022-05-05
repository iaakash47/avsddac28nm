
# POTENTIOMETRIC  10BIT DIGITAL-TO-ANALOG CONVERTER(DAC)
* The project aims to design a 10-bit Potentiometric Digital to Analog Converter using end-to-end Synopsys Commercial EDA tool(Custom Complier). The target is to design 10-bit potentiometric DAC with 1.8v digital voltage and 1 off-chip external voltage reference using SAED_PDK 28_32nm technology node

# Table of Content
1. [Introduction](#introduction)
   * [DAC](#dac)
2. [EDA tools used to implement Potentiometric DAC](#eda-tools-used-to-implement-potentiometric-dac)
3. [Architecture](#architecture)
4. [IP Design Specifications](#ip-design-specifications)
5. [Implementation of 10Bit Potentiometric DAC](#implementation-of-10bit-potentiometric-dac)
6. [Pre-layout Designs](#pre-layout-designs)
   * [Switch](#switch)
   * [2-Bit DAC](#2-bit-dac)
   * [3-Bit DAC](#3-bit-dac)
   * [4-Bit DAC](#4-bit-dac)
   * [5-Bit DAC](#5-bit-dac)
   * [6-Bit DAC](#6-bit-dac)
   * [7-Bit DAC](#7-bit-dac)
   * [8-Bit DAC](#8-bit-dac)
   * [9-Bit DAC](#9-bit-dac)
   * [10-Bit DAC](#10-bit-dac)
7. [References](#references)
8. [Contributor](#contributor)
9. [Acknowledgments](#acknowledgments)

## Introduction 
#### DAC 
* In real world, most of the data available is in the form of analog in nature. We have two types of converters analog to digital converter and digital to analog converter. These two converting interfaces are essential to obtain the required operations of a processor to manipulate the data of digital electronic equipment and an analog electric equipment. Digital to Analog Converter (DAC) is a device that transforms digital data into an analog signal in order to interact with the real world. The digital signal is represented with a binary code, which is a combination of bits 0’s and 1’s. The digital data can be produced from a microprocessor, Field Programmable Gate Array (FPGA), or Application Specified Integrated Circuit (ASIC). There are two commonly used DAC conversions – Weighed resistors method and R-2R ladder network method. Applications of a DAC: audio amplifier, video encoder, display electronics, data acquisition systems, calibration, Digital potentiometer.

* A n-bit Digital to Analog Converter (DAC) takes a n-bit digital word and converts it into a proportional analog voltage with respect to the reference voltage. The potentiometric DAC uses the concept of Voltage Divider. In an N-bit DAC, the analog voltage range, i.e. the Vref (here 1.8 V) is equally divided into 2^N voltage values. This is achieved by a series on 2^N equal resistors and taps are provided across each R. The combination of switches to tap the values is designed using the N-bit digital word as input. An example of N-bit potentiometric DAC is shown in the figure below.

* Two types of DACs :

  * Weighted Resistor DAC
  * R-2R Ladder DAC
  
 # Weighted Resistor DAC
 
 * A weighted resistor DAC produces an analog output, which is almost equal to the digital (binary) input by using binary weighted resistors in the inverting adder circuit. In short, a binary weighted resistor DAC is called as weighted resistor DAC.
  
 ### Weighted Resistor DAC Design
  ![166871259-dc9be251-84f7-4ac6-a7bb-7aed601f6f59](https://user-images.githubusercontent.com/88897605/166975942-7d4475cf-53b6-4cfa-a656-f3e70b055b37.png)

 # R-2R Ladder DAC
 
 * The R-2R Ladder DAC overcomes the disadvantages of a binary weighted resistor DAC. As the name suggests, R-2R Ladder DAC produces an analog output, which is almost equal to the digital (binary) input by using a R-2R ladder network in the inverting adder circuit.

 # R-2R Ladder DAC Design
 ![166871272-ec5a78ad-90d0-40e3-b2f7-2d93ae7eedcf](https://user-images.githubusercontent.com/88897605/166976030-1b324333-e676-4035-a8fa-f239b96098d5.png)

 
### Switch Reference Design
![switch circuit](https://user-images.githubusercontent.com/88897605/166973863-b4e730ad-2d92-46b2-9e24-0f59a315f0de.png)

The switches are designed as shown in the figure above. The digital voltage of 1.8V or 0V is given at the digital input port for logic 1 and 0 respectively. If the digital input is logic 1, then Vin1 appears at the output port, else Vin2 appears at the output. Hence this switch circuit replaces two switches in same level as it takes into account both the swiches of complemented and uncomplemented bit.

## EDA tools used to implement Potentiometric DAC
* The design has been built using Commericial EDA tools like Synopsys Custom Compiler. The library used is SAED32_28nm. 
* This design is implemented using 
  * Custom Compiler
  * Prime wave 
  * IC validator 
  * HSPICE 


### Terminal Functions
|Name	   |	I/O |	Description       |
|:-------|:----|:------------------|
|D [0:9] |I	  |Digital inputs     |
|VOUT	|O	|DAC analog voltage output|
|VDDA	|I	|Analog voltage supply (1.8)|
|VSSA	|I	|Analog ground 0V|
|VREFH |I	|Reference voltage low for DAC|
 

## Architecture
* ![dac](https://user-images.githubusercontent.com/88897605/166301140-92768886-3d0a-4183-9fb3-997a2d01b8b7.png)


## IP Design Specifications
![dac](https://user-images.githubusercontent.com/88897605/166930434-7ad9894c-a916-41a3-841c-8ed220ca2c75.png)



## Implementation of 10Bit Potentiometric DAC
The basic idea is to divide the voltage into N different voltage values in the range of VREFH and VREFL- for an N-Bit DAC. The design used here to achieve this is the simple resistor string DAC which consists of resistors in series. These resistors are then connected to various switches in such a fashion that it routes the exact voltage to the output. The problem of the largeness of the circuit is reduced by building hierarchical subcircuits of 10-Bit potentiometric DAC – Switch, 2-bit, 3-bit, 4-bit, 5-bit, 6-bit, 7-bit, 8-bit, 9-bit and 10-bit.

## Pre-layout Designs

# Switch 

### Terminal Functions
|Name	   | Value |	Description       |
|:-------|:----|:------------------|
|D_in |v1 = 0V, v2 = 1.05V, tr = 0.1us|Digital inputs|
|Capacitor|1pf|DAC analog voltage output|
|VDDA	|1.8v|Analog voltage supply (1.8v)|
|VSSA	|0v|Analog ground 0V|
|VREFH |1.2v|Reference voltage High for DAC|
|VREFL |0.8v|Reference voltage low for DAC|
 
## Switch design and simulation
![DAC_switch_new_schematic](https://user-images.githubusercontent.com/88897605/164980036-8a6a371a-60a2-44fa-aed5-81e3a3d4a516.png)

## Switch Symbol
![DAC_switch_new_symbol](https://user-images.githubusercontent.com/88897605/166885046-1129f3dd-f97e-47ed-979c-5d2ae9dde6f9.png)

## Switch Testbench
![DAC_switch_new_tb_schematic](https://user-images.githubusercontent.com/88897605/164980035-49c24338-c269-4788-86b3-42bdb9d447fe.png)

## Switch Waveform
![switch-waveform](https://user-images.githubusercontent.com/88897605/164980342-ab3aaf4f-ec4d-45c6-aee4-a8c5a7dc5f3d.png)


# 2-Bit DAC
#### specification

|Name	   | Value |	Description       |
|:-------|:----|:------------------|
|D_in |v1 = 0V, v2 = 1.05V, tr = 0.1us|Digital inputs|
|Resistor|200ohms|Resistance|
|Capacitor|5pf|Capacitance|
|VDDA	|1.8v|Analog voltage supply (1.8v)|
|VSSA	|0v|Analog ground 0V|
|VREFH |1.2v|Reference voltage High for DAC|
|VREFL |0.8v|Reference voltage low for DAC|

* 2-Bit DAC is implemented using 3 switch instances. 2-Bit circuitry and waveform are shown below

## 2-Bit DAC design and simulation:

* For the 2 bit DAC, switch circuit was included as a subcircuit. After creating the schematics, the spice netlist was extracted. The necessary model files of SAED32nm tt transistors were included in the netlist and transient analysis was performed.
* 
![DAC_2bit_DAC_schematic](https://user-images.githubusercontent.com/88897605/164980052-c9267798-0e0c-4e09-8dbd-df99a88a3fcf.png)

## Symbol
![DAC_2bit_DAC_symbol](https://user-images.githubusercontent.com/88897605/166305982-b176d1ba-3e4d-42fe-be1b-c510134b4e0a.png) 

## 2-Bit DAC Testbench

![DAC_2bit_DAC_tb_schematic](https://user-images.githubusercontent.com/88897605/164980051-02f01f98-b61e-4f4f-8cfa-ca63fd263b18.png)

## 2-Bit DAC Waveform
![dac_2bit](https://user-images.githubusercontent.com/88897605/164980353-51b860fb-8e18-47e8-bcd5-9a51e549ec8c.png)


# 3-Bit DAC

* 3Bit DAC is implemented using 2 2-Bit DACs and 1 switch instances. 3-Bit circuitry and waveform are shown below 

## 3-Bit DAC design and simulation: 
![DAC_3bit_DAC_schematic](https://user-images.githubusercontent.com/88897605/164980065-6536e03c-4f02-43dc-8804-e0a299fdc022.png)

## Symbol
![DAC_3bit_DAC_symbol](https://user-images.githubusercontent.com/88897605/166306032-f693086e-0100-4ce9-9045-ae91179ec3a3.png)

## 3-Bit DAC Testbench

![DAC_3bit_DAC_tb_schematic](https://user-images.githubusercontent.com/88897605/164980063-7f5c6e64-2d25-461c-94cd-a9ba2d1ac726.png)

## 3-Bit DAC Waveform
![dac_3bit](https://user-images.githubusercontent.com/88897605/164980361-9318aa81-3cdd-4747-8d2f-4b1e57e2be24.png)
![3bit_DAC](https://user-images.githubusercontent.com/88897605/166882530-39647bd1-30d8-41dc-bf95-a1bd6804d518.png)



# 4-Bit DAC

* 4Bit DAC is implemented using 2 and 3-Bit DACs and 1 switch instances. 4-Bit circuitry and waveform are shown below

## 4-Bit DAC design and simulation: 
![DAC_4bit_DAC_schematic](https://user-images.githubusercontent.com/88897605/164980075-4c164a56-2e68-4562-9b68-fd0466a0b620.png)

## Symbol
![DAC_4bit_DAC_symbol](https://user-images.githubusercontent.com/88897605/166306055-c78eeac3-5d05-4e6e-9f21-60a6fb45f77a.png)

## 4-Bit DAC Testbench

![DAC_4bit_DAC_tb_schematic](https://user-images.githubusercontent.com/88897605/164980073-2d32ac0b-f2fe-4e3e-8254-6751ebca17d7.png)

## 4-Bit DAC Waveform
![dac_4bit](https://user-images.githubusercontent.com/88897605/164980370-6271729e-dc16-4fdb-bcf8-f9aa55bf5534.png)
![4bit_DAC](https://user-images.githubusercontent.com/88897605/166882465-dbe752be-ec3a-40f8-8106-8300533e7ba7.png)



# 5-Bit DAC

* 5Bit DAC is implemented using 2 and 4-Bit DACs and 1 switch instances. 5-Bit circuitry and waveform are shown below

## 5-Bit DAC design and simulation:
![DAC_5bit_DAC_schematic](https://user-images.githubusercontent.com/88897605/164980093-02bc5682-28bd-43c2-a35e-8cd6af14dcaa.png)

## Symbol
![DAC_5bit_DAC_symbol](https://user-images.githubusercontent.com/88897605/166306076-15f5cabf-6904-4a29-8222-128fab83d39c.png)

## 5-Bit DAC Testbench
![DAC_5bit_DAC_tb_schematic](https://user-images.githubusercontent.com/88897605/164980091-5b051c25-71f1-4d10-a543-55f8f0d9e3ec.png)

## 5-Bit DAC Waveform
![dac_5bit](https://user-images.githubusercontent.com/88897605/164980375-1c7f4dd3-d7ef-47bb-9703-21cfacebcb09.png)
![5bit_DAC](https://user-images.githubusercontent.com/88897605/166882383-23b45316-f0bc-44f9-b7f4-161cde70cef0.png)



# 6-Bit DAC

* 6Bit DAC is implemented using 2 and 5-Bit DACs and 1 switch instances. 6-Bit circuitry and waveform are shown below

## 6-Bit DAC design and simulation:
![DAC_6bit_DAC_schematic](https://user-images.githubusercontent.com/88897605/164980114-d9121f6e-728c-4b42-91ee-aad19d387edc.png)

## Symbol
![DAC_6bit_DAC_symbol](https://user-images.githubusercontent.com/88897605/166306091-82979f6f-25ea-490c-9be2-3bd116ac5e16.png)

## 6-Bit DAC Testbench

![DAC_6bit_DAC_tb_schematic](https://user-images.githubusercontent.com/88897605/164980113-a9d0762b-c59c-4dc8-ab83-8a7d52f5f0b9.png)

## 6-Bit DAC Waveform
![dac_6bit](https://user-images.githubusercontent.com/88897605/164980379-7fc6f6e4-e903-436d-80b6-ac6e91907a43.png)
![6bit_DAC](https://user-images.githubusercontent.com/88897605/166882340-94fcaaba-6eef-4c38-96ac-a45bc68618c3.png)



# 7-Bit DAC

* 7Bit DAC is implemented using 2 and 6-Bit DACs and 1 switch instances. 7-Bit circuitry and waveform are shown below

## 7-Bit DAC design and simulation:
![DAC_7bit_DAC_schematic](https://user-images.githubusercontent.com/88897605/164980133-b7fcbdf5-0eab-4792-abc6-2ef10252a20a.png)

## Symbol
![DAC_7bit_DAC_symbol](https://user-images.githubusercontent.com/88897605/166306108-15bb8e59-74c1-4cb4-a72a-2a2f3f01df3a.png)

## 7-Bit DAC Testbench

![DAC_7bit_DAC_tb_schematic](https://user-images.githubusercontent.com/88897605/164980132-11eba075-33e1-4b07-b85c-5c7a38911741.png)

## 7-Bit DAC Waveform
![dac_7bit](https://user-images.githubusercontent.com/88897605/164980389-44fca3a8-28f3-4a77-b1a5-e0fd2468956e.png)

![7bit_DAC](https://user-images.githubusercontent.com/88897605/166882311-04b45756-5e68-4a9b-973e-31dca3c88186.png)



# 8-Bit DAC

* 8Bit DAC is implemented using 2 and 7-Bit DACs and 1 switch instances. 8-Bit circuitry and waveform are shown below

## 8-Bit DAC design and simulation:

![DAC_8bit_DAC_schematic](https://user-images.githubusercontent.com/88897605/164980147-5e51fbf7-9fe6-4529-a62d-d8589366d061.png)

## Symbol
![DAC_8bit_DAC_symbol](https://user-images.githubusercontent.com/88897605/166306121-e3f45c05-8483-4555-9396-0ebadb9a4494.png)

## 8-Bit DAC Testbench

![DAC_8bit_DAC_tb_schematic](https://user-images.githubusercontent.com/88897605/164980145-64d82a5b-21c7-4bfa-8eee-7ca944f6e6bc.png)

## 8-Bit DAC Waveform
![8bitwf_dac](https://user-images.githubusercontent.com/88897605/164980404-b4aefcdf-f052-4f88-a771-49626bf152c1.png)

![8bit_DAC](https://user-images.githubusercontent.com/88897605/166882259-17cdd7f5-07fe-431d-b797-98ee1251bdfe.png)



# 9-Bit DAC

* 9Bit DAC is implemented using 2 and 8-Bit DACs and 1 switch instances. 9-Bit circuitry and waveform are shown below

## 9-Bit DAC design and simulation:
![DAC_9bit_DAC_schematic](https://user-images.githubusercontent.com/88897605/164980158-bb4b294b-e96b-48eb-b3d0-b9242e75da15.png)

## Symbol
![DAC_9bit_DAC_symbol](https://user-images.githubusercontent.com/88897605/166306145-9bf78e2d-26a7-4012-bd6f-fd7b5a369fc7.png)

## 9-Bit DAC Testbench

![DAC_9bit_DAC_tb_schematic](https://user-images.githubusercontent.com/88897605/164980156-6c773642-8bba-4103-b124-86a1a7563557.png)

## 9 bit DAC waveform
![9bit_DAC](https://user-images.githubusercontent.com/88897605/164980838-c7068fd8-92ea-423a-9e28-2945823d1f98.png)
![10bit_DAC](https://user-images.githubusercontent.com/88897605/166895511-83da0a55-ef69-4a4a-ac0c-46a6b1daf717.png)



# 10-Bit DAC

* 10Bit DAC is implemented using 2 and 9-Bit DACs and 1 switch instances. 10-Bit circuitry and waveform are shown below

## 10-Bit DAC design and simulation:
![DAC_10bit_DAC_schematic](https://user-images.githubusercontent.com/88897605/164980177-9cf0e6a4-1158-41fc-b02a-b7c8e219aadb.png)


## Symbol
![DAC_10bit_DAC_symbol](https://user-images.githubusercontent.com/88897605/166306167-a2e945b4-525c-456c-b884-d1a47350b0e5.png)

## 10-Bit DAC Testbench

![DAC_10bit_DAC_tb_schematic](https://user-images.githubusercontent.com/88897605/164980174-120c793a-5acd-4902-be25-e3205dc2615e.png)

## 10 bit DAC waveform

![10bitDAC](https://user-images.githubusercontent.com/88897605/164980476-01544d4a-1c24-44c8-b08e-4427af935878.png)
![10bit_DAC](https://user-images.githubusercontent.com/88897605/166895511-83da0a55-ef69-4a4a-ac0c-46a6b1daf717.png)


# Note
* For 3 Bit DAC : D0, D1 and D2
* For 4 Bit DAC : D0, D1, D2 and D3 and so on.
* For 10 Bit DAC : D0, D1, D2...., D9.
* Other Inputs value remains the same as 2 Bit DAC until 10 Bit DAC.
* For 2 Bit DAC, Number of steps in the output graph = 2^N, i.e, 2^2 = 4 steps
* For a 10 Bit DAC, Number of steps in the output graph = 2^N, i.e, 2^10 = 1024 steps.
* The graph value for DAC ranges from VrefH (1.8V) to VrefL (0V).



# Further Work

* Need to start with custom layout for implementing 10 bit DAC

# References
- Sammer Duroji VSD team
- Kanna Shalini VSD team
- Skandha Deepsita VSD team 


# Contributor
* Aakash.K</br>
  Contact:iaakashkrish@gmail.com</br>
* Kunal Ghosh, Co-founder, VLSI SYSTEM DESIGN (VSD) Corp Pvt.Ltd - kunalpghosh@gmail.com

# Acknowledgments
* Kunal Ghosh, Co-founder, VLSI SYSTEM DESIGN (VSD) Corp Pvt.Ltd - kunalpghosh@gmail.com
* Muthukrishnan Chinnasamy, CEO of Semiconductor Fabless Accelerator Lab(SFAL)
* Montu Makadia - Semiconductor Fabless Accelerator Lab (SFAL)








