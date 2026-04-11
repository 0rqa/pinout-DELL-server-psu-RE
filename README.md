# Reverse engineering DELL server psu

>[!Caution]
> Disclaimer / Reverse Engineering Notice: <br> 
> All information, diagrams, and schematics in this repository were obtained through independent reverse engineering, measurement, and observation. 
> No proprietary, confidential, or leaked documents were used directly to create this content. 
> All pin assignments, signal mappings, and layouts represent independent analysis and do not reproduce any proprietary documentation. <br> <br>
> This project is intended for educational, research, and interoperability purposes only. 
> Commercial use of patented or proprietary technologies is not authorized by this notice.

<br>

>[!NOTE]
> All information in this repository is provided in good faith but may contain inaccuracies.

<br>

---

<br>

![image](https://github.com/0rqa/pinout-DELL-server-psu-RE/blob/main/pictures/schema_dell_psu%20.png)

|pin|description|explanation|
|-|-|-|
|FP1|main/standby 12V-  |system ground, connected to PE. For connecting PSUs in series, it's necessary to have grounded only the first PSU. Other PSUs in series need to be isolated.|
|FP2|main 12V+ | powered on when PSU is switched on|
|BP1|main 12V+ | powered on when PSU is switched on|
|BP2|main/standby 12V-|system ground, connected to PE. For connecting PSUs in series, it's necessary to have grounded only the first PSU. Other PSUs in series need to be isolated.|
|BP3|standby 12V+ | powered on when PSU is connected to AC|
|FIO1|PSU_detect|Internally 220 ohm pull-down |
|FIO2|/|/|
|FIO3|/|/|
|FIO4|DC_OK|High when the 12V rail is in spec, Low when the 12V rail is out of spec (10.5V-15V)|
|FIO5|AC_OK|High when the AC is in specified range (90-264VAC). Low when AC isn't present or is out of range. |
|FIO6|IO_GND|Common IO ground tied to PE|
|FIO7|SHARE|PSU supports up to six PSUs in parallel. For load balancing, connect all FIO7 together.|
|FIO8|/|/|
|FIO9|PSU_fault|Low when PSU indicates fault. High in normal operation|
|FIO10|IO_GND|Common IO ground tied to PE|
|FIO11|/|/|
|FIO12|/|/|
|BIO1|ON|Outside 3.3V pull-up, pull-down to enable the PSU, to wake the PSU from standby you also need to pull down the BIO2|
|BIO2|KILL|Pull-down to enable, to wake the PSU from standby you also need to pull down the BIO1|
|BIO3|/|/|
|BIO4|IO_GND|Common IO ground tied to PE|
|BIO5|SDA|PMBus data 3.3V, hardcoded I2C address 0xB0, in case of using more than one PSU an I2C expander/switch or more dedicated I2C buses are necessary. When using more than one PSU it's recommended to tie all 12V+ standby rails together. If not done, the other PSU will only communicate when AC is present.|
|BIO6|IO_GND|Common IO ground tied to PE|
|BIO7|SCL|PMBus clock 3.3V|
|BIO8|IO_GND|Common IO ground tied to PE|
|BIO9|/|/|
|BIO10|IO_GND|Common IO ground tied to PE|
|BIO11|/|/|
|BIO12|/|/|
