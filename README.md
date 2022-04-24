
# POTENTIOMETRIC DIGITAL-TO-ANALOG CONVERTER
* The project aims to design a 10-bit Potentiometric Digital to Analog Converter using end-to-end Synopsys Commercial EDA tool(Custom Complier). The target is to design 10-bit potentiometric DAC with 1.8v digital voltage and 1 off-chip external voltage reference using SAED_PDK 28_32nm technology node


## Introduction 
#### DAC 
* Digital to Analog Converter (DAC) is a device that transforms digital data into an analog signal in order to interact with the real world. The digital signal is represented with a binary code, which is a combination of bits 0’s and 1’s. The digital data can be produced from a microprocessor, Field Programmable Gate Array (FPGA), or Application Specified Integrated Circuit (ASIC). There are two commonly used DAC conversions – Weighed resistors method and R-2R ladder network method. Applications of a DAC: audio amplifier, video encoder, display electronics, data acquisition systems, calibration, Digital potentiometer.

## IP Design Specifications
![IMG_20220424_193255](https://user-images.githubusercontent.com/88897605/164980282-f160bc82-98d2-4270-bd8e-ae72c9e464be.jpg)


## Implementation of 10Bit Potentiometric DAC
The design used here to achieve this is the simple resistor string DAC which consists of resistors in series. These resistors are then connected to various switches in such a fashion that it routes the exact voltage to the output. The problem of the largeness of the circuit is reduced by building hierarchical subcircuits of 10-Bit potentiometric DAC – Switch, 2-bit, 3-bit, 4-bit, 5-bit, 6-bit, 7-bit, 8-bit, 9-bit and 10-bit and is to divide the voltage into N different voltage values in the range of VREFH and VREFL- for an N-Bit DAC.

## Pre-layout Designs

## Switch design and simulation

![DAC_switch_new_tb_schematic](https://user-images.githubusercontent.com/88897605/164980035-49c24338-c269-4788-86b3-42bdb9d447fe.png)
![DAC_switch_new_schematic](https://user-images.githubusercontent.com/88897605/164980036-8a6a371a-60a2-44fa-aed5-81e3a3d4a516.png)
![switch-waveform](https://user-images.githubusercontent.com/88897605/164980342-ab3aaf4f-ec4d-45c6-aee4-a8c5a7dc5f3d.png)

 
## 2-Bit DAC design and simulation:
 ![DAC_2bit_DAC_tb_schematic](https://user-images.githubusercontent.com/88897605/164980051-02f01f98-b61e-4f4f-8cfa-ca63fd263b18.png)
![DAC_2bit_DAC_schematic](https://user-images.githubusercontent.com/88897605/164980052-c9267798-0e0c-4e09-8dbd-df99a88a3fcf.png)
![dac_2bit](https://user-images.githubusercontent.com/88897605/164980353-51b860fb-8e18-47e8-bcd5-9a51e549ec8c.png)


## 3-Bit DAC design and simulation: 
![DAC_3bit_DAC_tb_schematic](https://user-images.githubusercontent.com/88897605/164980063-7f5c6e64-2d25-461c-94cd-a9ba2d1ac726.png)
![DAC_3bit_DAC_schematic](https://user-images.githubusercontent.com/88897605/164980065-6536e03c-4f02-43dc-8804-e0a299fdc022.png)
![dac_3bit](https://user-images.githubusercontent.com/88897605/164980361-9318aa81-3cdd-4747-8d2f-4b1e57e2be24.png)


## 4-Bit DAC design and simulation: 
![DAC_4bit_DAC_tb_schematic](https://user-images.githubusercontent.com/88897605/164980073-2d32ac0b-f2fe-4e3e-8254-6751ebca17d7.png)
![DAC_4bit_DAC_schematic](https://user-images.githubusercontent.com/88897605/164980075-4c164a56-2e68-4562-9b68-fd0466a0b620.png)
![dac_4bit](https://user-images.githubusercontent.com/88897605/164980370-6271729e-dc16-4fdb-bcf8-f9aa55bf5534.png)


## 5-Bit DAC design and simulation:
![DAC_5bit_DAC_tb_schematic](https://user-images.githubusercontent.com/88897605/164980091-5b051c25-71f1-4d10-a543-55f8f0d9e3ec.png)
![DAC_5bit_DAC_schematic](https://user-images.githubusercontent.com/88897605/164980093-02bc5682-28bd-43c2-a35e-8cd6af14dcaa.png)
![dac_5bit](https://user-images.githubusercontent.com/88897605/164980375-1c7f4dd3-d7ef-47bb-9703-21cfacebcb09.png)


## 6-Bit DAC design and simulation:

![DAC_6bit_DAC_tb_schematic](https://user-images.githubusercontent.com/88897605/164980113-a9d0762b-c59c-4dc8-ab83-8a7d52f5f0b9.png)
![DAC_6bit_DAC_schematic](https://user-images.githubusercontent.com/88897605/164980114-d9121f6e-728c-4b42-91ee-aad19d387edc.png)
![dac_6bit](https://user-images.githubusercontent.com/88897605/164980379-7fc6f6e4-e903-436d-80b6-ac6e91907a43.png)


## 7-Bit DAC design and simulation:
![DAC_7bit_DAC_tb_schematic](https://user-images.githubusercontent.com/88897605/164980132-11eba075-33e1-4b07-b85c-5c7a38911741.png)
![DAC_7bit_DAC_schematic](https://user-images.githubusercontent.com/88897605/164980133-b7fcbdf5-0eab-4792-abc6-2ef10252a20a.png)
![dac_7bit](https://user-images.githubusercontent.com/88897605/164980389-44fca3a8-28f3-4a77-b1a5-e0fd2468956e.png)


## 8-Bit DAC design and simulation:

![DAC_8bit_DAC_tb_schematic](https://user-images.githubusercontent.com/88897605/164980145-64d82a5b-21c7-4bfa-8eee-7ca944f6e6bc.png)
![DAC_8bit_DAC_schematic](https://user-images.githubusercontent.com/88897605/164980147-5e51fbf7-9fe6-4529-a62d-d8589366d061.png)
![8bitwf_dac](https://user-images.githubusercontent.com/88897605/164980404-b4aefcdf-f052-4f88-a771-49626bf152c1.png)


## 9-Bit DAC design and simulation:

![DAC_9bit_DAC_tb_schematic](https://user-images.githubusercontent.com/88897605/164980156-6c773642-8bba-4103-b124-86a1a7563557.png)
![DAC_9bit_DAC_schematic](https://user-images.githubusercontent.com/88897605/164980158-bb4b294b-e96b-48eb-b3d0-b9242e75da15.png)
![9bit_DAC](https://user-images.githubusercontent.com/88897605/164980838-c7068fd8-92ea-423a-9e28-2945823d1f98.png)


## 10-Bit DAC design and simulation:

![DAC_10bit_DAC_tb_schematic](https://user-images.githubusercontent.com/88897605/164980174-120c793a-5acd-4902-be25-e3205dc2615e.png)
![DAC_10bit_DAC_schematic](https://user-images.githubusercontent.com/88897605/164980177-9cf0e6a4-1158-41fc-b02a-b7c8e219aadb.png)
![10bitDAC](https://user-images.githubusercontent.com/88897605/164980476-01544d4a-1c24-44c8-b08e-4427af935878.png)



# References
- Sammer Duroji VSD team


# Contributor
Aakash.K</br>
Contact:iaakashkrish@gmail.com</br>

Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalpghosh@gmail.com

# Acknowledgments
Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalpghosh@gmail.com









