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

## BOM 

> Parts are sourced from JLCPCB/LCSC during ordering

```csv
Ref,Qty,Part,Package,Notes
U1,1,ESP32-S3-WROOM-1,Module,ESP32-S3 module (pick N16R8 if you want more memory)
U2,1,CH340C,SOIC-16,USB-UART for flashing + serial
U3,1,MP2303ADN,SOIC-8-EP,5V->3.3V buck regulator
L1,1,4.7uH Shielded Inductor,SWPA4012 (example),Match PCB footprint; target Isat >= 2A
D1,1,Schottky Diode (SS14 or equivalent),SOD-123,USB VBUS -> board 5V rail protection
D2,3,ESD Diode (USB protection),SOT-23,Optional but recommended
D5,2,Addressable RGB LED (SK6805),SK6805,NeoPixel-style LEDs (needs code)
D7,1,Indicator LED,0603,Power/status LED
S1,1,Tactile Switch,TS-1088,RESET
S2,1,Tactile Switch,TS-1088,BOOT
S3,1,Tactile Switch,TS-1088,USER button (optional)
R_CC1,2,5.1k Resistor,0603,USB-C CC resistors
R_BOOT_EN,2,10k Resistor,0603,Pull-ups for BOOT/EN
R_LED_DATA,2,330 Resistor,0603,Series resistor for RGB LED DIN
R_SENSE,2,100k Resistor,0603,Battery sense divider
C_IN,1,22uF Capacitor,1206,Buck input bulk cap (X5R/X7R >=10V)
C_OUT,2,22uF Capacitor,1206,Buck output bulk caps (X5R/X7R >=10V)
C_DEC,Multiple,100nF Capacitor,0603,Decoupling near ICs/LEDs
C_MISC,1,1uF Capacitor,0603,EN reset RC (if used)
J1,1,USB-C Connector,Custom footprint,Must match PCB footprint exactly
J2,1,Pin Header 2.54mm,1xN,GPIO breakout ( hand-soldered )
J4,1,Pin Header 2.54mm,1xN,GPIO breakout ( hand-soldered)
J5,1,Pin Header 2.54mm,1xN,GPIO breakout (hand-soldered)

