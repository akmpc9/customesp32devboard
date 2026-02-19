# customesp32devboard
# Custom ESP32-S3 Dev Board (v1)

A custom **ESP32-S3** development board designed to be **reliable**, **good-quality**, and **feature-rich** for **learning + teaching electronics** (power, USB, routing, GPIO, LEDs/buttons, battery monitoring).

---

## Images

![Schematic](schematic.png)

![Routing](route.png)

![3D View](view.png)

---

## Project goals

- Make a **robust ESP32-S3 platform** (clean power + clean layout)
- Break out lots of GPIO for experiments
- Add useful learning features (LEDs, buttons, battery sense, USB programming)
- Be easy to reproduce and improve (v1 → v2)

---

## Key features (v1)

- **ESP32-S3-WROOM-1** module (Wi-Fi + BLE)
- **USB-C** connector
- **CH340C** USB-UART for flashing/serial
- **5V → 3.3V buck converter** (efficient vs linear regulators)
- **Auto-program** support (EN/BOOT control from USB-UART)
- **GPIO headers** for prototyping
- **User button** + indicator LEDs
- **Battery sense divider** (read VBAT on an ADC pin)
- Layout rules applied: antenna keepout, USB routing, buck SW isolation, ground plane

---

## Flashing / serial

- Plug USB-C into your PC
- Select the **CH340** COM port
- Use Arduino IDE or PlatformIO (ESP32-S3 target)

---

## BOM (CSV)

> Exported from KiCad. Parts are intended to be sourced via JLCPCB/LCSC 

```csv
Designator (Top),Designator (Bottom),Qty,Value / Comment,KiCad Footprint,LCSC Part #,MPN,Manufacturer,Lib,Category,Description,Product link,Notes / Warnings,Source,Total Price (USD)
C1,,20,1uF,Capacitor_SMD:C_0603_1608Metric,C15849,,Samsung Electro-Mechanics,Basic,Multilayer Ceramic Capacitors MLCC - SMD/SMT,1uF 50V X5R ±10% 0603 Multilayer Ceramic Capacitors MLCC - SMD/SMT ROHS,https://jlcpcb.com/partdetail/16531-CL10A105KB8NNNC/C15849,,20 JLCPCB,0.112
"C2,C4,C6,CBST1,CCH340C1,CCH340C2,CIN2,CLED1,CLED2",,55,100nF,Capacitor_SMD:C_0603_1608Metric,C14663,,YAGEO,Basic,Multilayer Ceramic Capacitors MLCC - SMD/SMT,100nF 50V X7R ±10% 0603 Multilayer Ceramic Capacitors MLCC - SMD/SMT ROHS,https://jlcpcb.com/partdetail/YAGEO-CC0603KRX7R9BB104/C14663,"1.There may be multiple types of parts, but one type of part has been matched. Please check.;",55 JLCPCB,0.143
"C3,CIN1,COUT1,COUT2",,24,22uF,Capacitor_SMD:C_1206_3216Metric,C12891,,Samsung Electro-Mechanics,Basic,Multilayer Ceramic Capacitors MLCC - SMD/SMT,22uF 25V X5R ±10% 1206 Multilayer Ceramic Capacitors MLCC - SMD/SMT ROHS,https://jlcpcb.com/partdetail/13537-CL31A226KAHNNNE/C12891,"1.There may be multiple types of parts, but one type of part has been matched. Please check.;",24 JLCPCB,1.1424
C5,,20,10uF,Capacitor_SMD:C_0603_1608Metric,C19702,,Samsung Electro-Mechanics,Basic,Multilayer Ceramic Capacitors MLCC - SMD/SMT,10V 10uF X5R ±10% 0603 Multilayer Ceramic Capacitors MLCC - SMD/SMT ROHS,https://jlcpcb.com/partdetail/20411-CL10A106KP8NNNC/C19702,,20 JLCPCB,0.13
CCOMP1,,20,3.9nF,Capacitor_SMD:C_0603_1608Metric,C1618,,FH (Guangdong Fenghua Advanced Tech),Extended,Multilayer Ceramic Capacitors MLCC - SMD/SMT,3.9nF 50V X7R ±10% 0603 Multilayer Ceramic Capacitors MLCC - SMD/SMT ROHS,https://jlcpcb.com/partdetail/1970-0603B392K500NT/C1618,,20 JLCPCB,0.064
CSS1,,20,10nF,Capacitor_SMD:C_0603_1608Metric,C57112,,FH (Guangdong Fenghua Advanced Tech),Basic,Multilayer Ceramic Capacitors MLCC - SMD/SMT,10nF 50V X7R ±10% 0603 Multilayer Ceramic Capacitors MLCC - SMD/SMT ROHS,https://jlcpcb.com/partdetail/58143-0603B103K500NT/C57112,,20 JLCPCB,0.056
D1,,15,1N5819HW-7-F,Diode_SMD:D_SOD-123,C82544,,Diodes Incorporated,Extended,Schottky Diodes,-65℃~+150℃ 1 Independent 1A 1mA@40V 25A 40V 450mV@1A SOD-123 Schottky Diodes ROHS,https://jlcpcb.com/partdetail/DiodesIncorporated-1N5819HW_7F/C82544,,15 JLCPCB,0.4365
"D2,D3,D4",,21,LESD5D5.0CT1G,LESD5D5.0CT1G:TVS_LESD5D5.0CT1G,C5199850,,"UMW(Youtai Semiconductor Co., Ltd.)",Extended,ESD And Surge Protection (TVS/ESD),-40℃~+125℃ 15pF 18.6V 1uA 5V 7.8V 9.4A@8/20us IEC 61000-4-2、IEC 61000-4-4 TVS SOD-523 ESD and Surge Protection (TVS/ESD) ROHS,https://jlcpcb.com/partdetail/5885882-LESD5D5_0CT1G_UMW/C5199850,1.The comment (LESD5D5.0CT1G(UMW)) of this part does not match the one (LESD5D5.0CT1G) provided in your BOM. Please confirm;,21 JLCPCB,0.3087
"D5,D6",,12,SK6805,LED_SMD:LED_SK6805_PLCC4_2.4x2.7mm_P1.3mm,C2890035,,OPSCO Optoelectronics,Extended,RGB LEDs(Built-In IC),"-40℃~+80℃ 0.5mA 0.65mm 1.5mm 1.5mm 160° 1kHz 2000V 3.5V~5.5V 800Kbit/s R:50mcd~100mcd、G:120mcd~240mcd、B:20mcd~40mcd R:620nm~625nm、G:520nm~530nm、B:460nm~470nm Semi-transparent lens SMD-4P,1.5x1.5mm RGB LEDs(Built-in IC) ROHS",https://jlcpcb.com/partdetail/OPSCOOptoelectronics-SK6805EC15/C2890035,1.The comment (SK6805-EC15) of this part does not match the one (SK6805) provided in your BOM. Please confirm;,12 JLCPCB,1.2312
D7,,20,SM0603UYC,SM0603UYC:LED_SM0603UYC,C2287,,Hubei KENTO Elec,Extended,LED Indication - Discrete,-40℃~+85℃ 120° 175mcd 2.4V 40mW 584nm~594nm 596nm Discrete Diode Water Clear Yellow 0603 LED Indication - Discrete ROHS,https://jlcpcb.com/partdetail/Hubei_KENTOElec-KT0603Y/C2287,1.The comment (KT-0603Y) of this part does not match the one (SM0603UYC) provided in your BOM. Please confirm;,20 JLCPCB,0.206
J1,,5,TYPE-C-31-M-12,TYPE-C-31-M-12:HRO_TYPE-C-31-M-12,C165948,,Korean Hroparts Elec,Extended,USB Connectors,"-30℃~+80℃ 1 10,000 cycles 16P 20V 5A 7.35mm Female Surface Mount, Right Angle Type-C SMD USB Connectors ROHS",https://jlcpcb.com/partdetail/Korean_HropartsElec-TYPE_C_31_M12/C165948,,5 JLCPCB,0.9055
L1,,9,4.7uH,Inductor_SMD:L_Sunlord_SWPA4012S,C316363,,Sunlord,Extended,Power Inductors,"4.7uH ±20% SMD,4x4mm Power Inductors ROHS",https://jlcpcb.com/partdetail/Sunlord-SWPA4012S4R7MT/C316363,,9 JLCPCB,0.6219
"Q1,Q2",,15,MMBT3904,Package_TO_SOT_SMD:SOT-23,C7420353,,hongjiacheng,Extended,Bipolar (BJT),-55℃~+150℃ 1 NPN 100 100nA 200mA 200mW 300MHz 300mV 40V 6V NPN SOT-23 Bipolar (BJT) ROHS,https://jlcpcb.com/partdetail/hongjiacheng-MMBT3904/C7420353,,15 JLCPCB,0.1335
"R1,R2",,20,5k1,Resistor_SMD:R_0603_1608Metric,C23186,,UNI-ROYAL(Uniroyal Elec),Basic,Chip Resistor - Surface Mount,-55℃~+155℃ 100mW 5.1kΩ 75V Thick Film Resistor ±1% ±100ppm/℃ 0603 Chip Resistor - Surface Mount ROHS,https://jlcpcb.com/partdetail/23913-0603WAF5101T5E/C23186,1.The comment (0603WAF5101T5E) of this part does not match the one (5k1) provided in your BOM. Please confirm;,20 JLCPCB,0.024
"R3,R7",,20,10k,Resistor_SMD:R_0805_2012Metric,C17414,,UNI-ROYAL(Uniroyal Elec),Basic,Chip Resistor - Surface Mount,-55℃~+155℃ 10kΩ 125mW 150V Thick Film Resistor ±1% ±100ppm/℃ 0805 Chip Resistor - Surface Mount ROHS,https://jlcpcb.com/partdetail/18102-0805W8F1002T5E/C17414,1.The comment (0805W8F1002T5E) of this part does not match the one (10k) provided in your BOM. Please confirm;,20 JLCPCB,0.044
"R5,R6",,20,4.7k,Resistor_SMD:R_0603_1608Metric,C23162,,UNI-ROYAL(Uniroyal Elec),Basic,Chip Resistor - Surface Mount,-55℃~+155℃ 100mW 4.7kΩ 75V Thick Film Resistor ±1% ±100ppm/℃ 0603 Chip Resistor - Surface Mount ROHS,https://jlcpcb.com/partdetail/23889-0603WAF4701T5E/C23162,1.The comment (0603WAF4701T5E) of this part does not match the one (4.7k) provided in your BOM. Please confirm;,20 JLCPCB,0.026
"R8,R9,R12,RBOT1",,30,10k,Resistor_SMD:R_0603_1608Metric,C25804,,UNI-ROYAL(Uniroyal Elec),Basic,Chip Resistor - Surface Mount,-55℃~+155℃ 100mW 10kΩ 75V Thick Film Resistor ±1% ±100ppm/℃ 0603 Chip Resistor - Surface Mount ROHS,https://jlcpcb.com/partdetail/26547-0603WAF1002T5E/C25804,"1.The comment (0603WAF1002T5E) of this part does not match the one (10k) provided in your BOM. Please confirm; 2.There may be multiple types of parts, but one type of part has been matched. Please check.;",30 JLCPCB,0.036
"R10,R11",,20,100k,Resistor_SMD:R_0603_1608Metric,C25803,,UNI-ROYAL(Uniroyal Elec),Basic,Chip Resistor - Surface Mount,-55℃~+155℃ 100kΩ 100mW 75V Thick Film Resistor ±1% ±100ppm/℃ 0603 Chip Resistor - Surface Mount ROHS,https://jlcpcb.com/partdetail/26546-0603WAF1003T5E/C25803,1.The comment (0603WAF1003T5E) of this part does not match the one (100k) provided in your BOM. Please confirm;,20 JLCPCB,0.022
RCOMP1,,20,12k,Resistor_SMD:R_0603_1608Metric,C22790,,UNI-ROYAL(Uniroyal Elec),Basic,Chip Resistor - Surface Mount,-55℃~+155℃ 100mW 12kΩ 75V Thick Film Resistor ±1% ±100ppm/℃ 0603 Chip Resistor - Surface Mount ROHS,https://jlcpcb.com/partdetail/23517-0603WAF1202T5E/C22790,,20 JLCPCB,0.024
"RLED1,RLED2",,20,330,Resistor_SMD:R_0603_1608Metric,C23138,,UNI-ROYAL(Uniroyal Elec),Basic,Chip Resistor - Surface Mount,-55℃~+155℃ 100mW 330Ω 75V Thick Film Resistor ±1% ±100ppm/℃ 0603 Chip Resistor - Surface Mount ROHS,https://jlcpcb.com/partdetail/23865-0603WAF3300T5E/C23138,1.The comment (0603WAF3300T5E) of this part does not match the one (330) provided in your BOM. Please confirm;,20 JLCPCB,0.026
RLED3,,20,3.3k,Resistor_SMD:R_0603_1608Metric,C22978,,UNI-ROYAL(Uniroyal Elec),Basic,Chip Resistor - Surface Mount,-55℃~+155℃ 100mW 3.3kΩ 75V Thick Film Resistor ±1% ±100ppm/℃ 0603 Chip Resistor - Surface Mount ROHS,https://jlcpcb.com/partdetail/23705-0603WAF3301T5E/C22978,,20 JLCPCB,0.024
RTOP1,,20,26.1k,Resistor_SMD:R_0603_1608Metric,C325725,,TyoHM,Extended,Chip Resistor - Surface Mount,-55℃~+155℃ 100mW 26.1kΩ 50V Thick Film Resistor ±1% ±100ppm/℃ 0603 Chip Resistor - Surface Mount ROHS,https://jlcpcb.com/partdetail/TyoHM-RMC060326_1K1N/C325725,1.The comment (RMC060326.1K1%N) of this part does not match the one (26.1k) provided in your BOM. Please confirm;,20 JLCPCB,0.064
"S1,S2,S3",,19,TS-1088-AR02016,TS-1088-AR02016:SW_TS-1088-AR02016,C720477,,XUNPU,Basic,Tactile Switches,"-30℃~+80℃ 1.6N 100,000 Cycles 12V 2mm 3mm 4mm 50mA Black Round Button SMD(SMT) Tab SPST Surface Mount,Vertical Without Bracket SMD,4x3mm Tactile Switches ROHS",https://jlcpcb.com/partdetail/XUNPU-TS_1088AR02016/C720477,,19 JLCPCB,0.9044
U1,,5,ESP32-S3-WROOM-1,RF_Module:ESP32-S3-WROOM-1,C2913202,,Espressif Systems,Extended,WiFi Modules,"-103.5dBm -40℃~+65℃ 2.4GHz 20.5dBm 355mA 3V~3.6V 95mA ESP32-S3R8 On-board PCB Antenna UART、SPI、I2C、GPIO、I2S、USB SMD,25.5x18mm WiFi Modules ROHS",https://jlcpcb.com/partdetail/3198300-ESP32_S3_WROOM_1N16R8/C2913202,1.The comment (ESP32-S3-WROOM-1-N16R8) of this part does not match the one (ESP32-S3-WROOM-1) provided in your BOM. Please confirm;,5 JLCPCB,28.456
U2,,5,CH340C,Package_SO:SOIC-16_3.9x9.9mm_P1.27mm,C7464026,,WCH(Jiangsu Qin Heng),Extended,USB Converters,SOP-16 USB Converters ROHS,https://jlcpcb.com/partdetail/WCH_Jiangsu_Qin_Heng-CH340C/C7464026,,5 JLCPCB,3.0735
U3,,5,MP2303ADN,Package_SO:SOIC-8-1EP_3.9x4.9mm_P1.27mm_EP2.62x3.51mm,C18876,,Monolithic Power Systems,Extended,DC-DC Converters,-40℃~+85℃@(TA) 1 360kHz 3A 4.7V~28V 800mV~25V Adjustable Buck Buck Built-in Yes SOIC-8-EP DC-DC Converters ROHS,https://jlcpcb.com/partdetail/19579-MP2303ADN_LFZ/C18876,,5 JLCPCB,22.653

TOTAL,,,,,,,,"=SUM(I2:I999)",


