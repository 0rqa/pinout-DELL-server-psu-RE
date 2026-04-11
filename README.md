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
> This repo is still being developed (WIP). All information in this repository is provided in good faith but may contain inaccuracies.

<br>

---

<br>

![image](https://github.com/0rqa/pinout-DELL-server-psu-RE/blob/main/pictures/schema_dell_psu.png)

|pin|description|explanation|
|-|-|-|
|FP1|main/standby 12V-  ||
|FP2|main 12V+ | powered on when psu is switch on|
|BP1|main 12V+ | powered on when psu is switch on|
|BP2|main/standby 12V-||
|BP3|standby 12V+ | powered on when psu is connected to AC|
|FIO1|||
|FIO2|/||
|FIO3|/||
|FIO4|||
|FIO5|||
|FIO6|||
|FIO7|||
|FIO8|/||
|FIO9|||
|FIO10|||
|FIO11|/||
|FIO12|/||
|BIO1|ON||
|BIO2|KILL||
|BIO3|/||
|BIO4|GND||
|BIO5|SDA||
|BIO6|GND||
|BIO7|SCL||
|BIO8|GND||
|BIO9|||
|BIO10|GND||
|BIO11|||
|BIO12|/||
