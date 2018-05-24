#ES9028Q2M DAC controller PCB

### 1. Spec
1.	RPi HAT size
2.	5V DC in from RPi GPIO 5V pin
3.	On board 3.3V LDO
4.	Minimum track width used: 0.3mm
5.	Minimum via hole used: 0.35mm
6.	Two layers 
7.	Tented via
### 2. Layout
1.	MCU pin #10 and pin #11 connects to RPi I2C SDA and SCL respectively.
2.	MCU pin #28 and pin #29 connects to DAC HAT I2C SDA and SCL respectively.
### 3. BoM
1.	C1, C4: LDO bypass capacitor, 10uF 10V, part#:  1206ZC106MAT2A
2.	C2, C3, C5: DVDD bypass capacitor, 2.2Uf 10V, part#: CC1206KKX7R6BB225
3.	R1, R2: I2C slave pull-up, 3.9K ohm 1%, part#: CRCW12063K90FKEAC
4.	R3: PDI CLK pull-up, optional, 10K ohm 1%, part#: CRCW120610K0FKEAC
5.	LDO:  part#: LM2937IMP-3.3/NOPB
6.	MCU: ATMEL Xmega 64A4U, part# ATXMEGA64A4U-AU
7.	PDI: MCU programming header, part # 67997-406HLF
8.	GPIOS: 20x2 SMT GPIO connector, female, connects to RPi, link: https://www.modmypi.com/electronics/headers-337/raspberry-pi-hat-socket-header-smt
9.	GPIOT: 20x2 SMT GPIO connector, male, connects to DAC HAT, link: https://www.ebay.com/itm/10pcs-RoHS-2-54mm-Pitch-2X40-Pin-Header-Strip-Double-Row-SMT-SMD-Male-PCB-Board/271556499758?epid=752838815&hash=item3f3a07592e:g:kWwAAOSwhMpTz-OF 
Note this is 2x40 connector, you need to cut them in half to make 2x20 connectors
### 4. Tested PDI programmer:

  Link: https://www.ebay.com/itm/Olimex-AVR-ISP-MK2-USB-Compatible-AVR-programmer-with-ICSP-PDI-TPI-Support/222686440093?ssPageName=STRK%3AMEBIDX%3AIT&_trksid=p2057872.m2749.l2649

Note: Disconnect the controller board from the RPi during programming. The programmer will supply the 3.3V through the PDI header. 

### 5. Related resouce
1.	MCU firmware design:

  https://github.com/VinnyLorrin/ES9028Q2M-controller

2.	MCU Linux ALSA driver:

  https://github.com/VinnyLorrin/ES9028-controller-Linux-Driver
