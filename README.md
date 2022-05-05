
# POTENTIOMETRIC DIGITAL-TO-ANALOG CONVERTER
* The project aims to design a 10-bit Potentiometric Digital to Analog Converter using end-to-end Synopsys Commercial EDA tool(Custom Complier). The target is to design 10-bit potentiometric DAC with 1.8v digital voltage and 1 off-chip external voltage reference using SAED_PDK 28_32nm technology node

# Table of Content
1. [Introduction](#introduction)
   * [DAC](#dac)
2. [IP Block Design](#ip-block-design)
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


## IP Block Design 
![109257152-7deed980-77c5-11eb-888c-805d33d2b3dc](https://user-images.githubusercontent.com/88897605/166885726-1fab3e52-f9b2-4617-86b3-a0021853e156.png)

## Architecture
* ![dac](https://user-images.githubusercontent.com/88897605/166301140-92768886-3d0a-4183-9fb3-997a2d01b8b7.png)


## IP Design Specifications
![IMG_20220424_193255](https://user-images.githubusercontent.com/88897605/164980282-f160bc82-98d2-4270-bd8e-ae72c9e464be.jpg)


## Implementation of 10Bit Potentiometric DAC
The basic idea is to divide the voltage into N different voltage values in the range of VREFH and VREFL- for an N-Bit DAC. The design used here to achieve this is the simple resistor string DAC which consists of resistors in series. These resistors are then connected to various switches in such a fashion that it routes the exact voltage to the output. The problem of the largeness of the circuit is reduced by building hierarchical subcircuits of 10-Bit potentiometric DAC – Switch, 2-bit, 3-bit, 4-bit, 5-bit, 6-bit, 7-bit, 8-bit, 9-bit and 10-bit.

## Pre-layout Designs

# Switch 

## Switch design and simulation
![DAC_switch_new_schematic](https://user-images.githubusercontent.com/88897605/164980036-8a6a371a-60a2-44fa-aed5-81e3a3d4a516.png)

## Switch Symbol
![DAC_switch_new_symbol](https://user-images.githubusercontent.com/88897605/166885046-1129f3dd-f97e-47ed-979c-5d2ae9dde6f9.png)

## Switch Testbench
![DAC_switch_new_tb_schematic](https://user-images.githubusercontent.com/88897605/164980035-49c24338-c269-4788-86b3-42bdb9d447fe.png)

## Switch Waveform
![switch-waveform](https://user-images.githubusercontent.com/88897605/164980342-ab3aaf4f-ec4d-45c6-aee4-a8c5a7dc5f3d.png)


# 2-Bit DAC

## 2-Bit DAC design and simulation:
![DAC_2bit_DAC_schematic](https://user-images.githubusercontent.com/88897605/164980052-c9267798-0e0c-4e09-8dbd-df99a88a3fcf.png)

## Symbol
![DAC_2bit_DAC_symbol](https://user-images.githubusercontent.com/88897605/166305982-b176d1ba-3e4d-42fe-be1b-c510134b4e0a.png) 

## 2-Bit DAC Testbench

![DAC_2bit_DAC_tb_schematic](https://user-images.githubusercontent.com/88897605/164980051-02f01f98-b61e-4f4f-8cfa-ca63fd263b18.png)

## 2-Bit DAC Waveform
![dac_2bit](https://user-images.githubusercontent.com/88897605/164980353-51b860fb-8e18-47e8-bcd5-9a51e549ec8c.png)


# 3-Bit DAC

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

## 10-Bit DAC design and simulation:
![DAC_10bit_DAC_schematic](https://user-images.githubusercontent.com/88897605/164980177-9cf0e6a4-1158-41fc-b02a-b7c8e219aadb.png)


## Symbol
![DAC_10bit_DAC_symbol](https://user-images.githubusercontent.com/88897605/166306167-a2e945b4-525c-456c-b884-d1a47350b0e5.png)

## 10-Bit DAC Testbench

![DAC_10bit_DAC_tb_schematic](https://user-images.githubusercontent.com/88897605/164980174-120c793a-5acd-4902-be25-e3205dc2615e.png)

## 10 bit DAC waveform

![10bitDAC](https://user-images.githubusercontent.com/88897605/164980476-01544d4a-1c24-44c8-b08e-4427af935878.png)
![10bit_DAC](https://user-images.githubusercontent.com/88897605/166895511-83da0a55-ef69-4a4a-ac0c-46a6b1daf717.png)





# Further Work
* Need to understand the basics of custom layout and rules for drawing layout 
* Not able to figure out which metal contact and vias to be used for interconnect
* issues with DRC,LVS errors 
* Able to understand the differences between layout editor and Schematic Driven layout 
* Need to get more familiar with tool for layout usage 
* Not able to generate Waveforms 

# References
- Sammer Duroji VSD team


# Contributor
Aakash.K</br>
Contact:iaakashkrish@gmail.com</br>
Kunal Ghosh, Co-founder, VLSI SYSTEM DESIGN (VSD) Corp Pvt.Ltd - kunalpghosh@gmail.com

# Acknowledgments
* Kunal Ghosh, Co-founder, VLSI SYSTEM DESIGN (VSD) Corp Pvt.Ltd - kunalpghosh@gmail.com
* Muthukrishnan Chinnasamy, CEO of Semiconductor Fabless Accelerator Lab(SFAL)
* Montu Makadia - Semiconductor Fabless Accelerator Lab (SFAL)








