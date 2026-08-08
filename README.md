# **3x3 Macro Pad Extras**

Documentation written by JStudios6118

This repository contains the KiCad design files and files for 3D printing the case of the board as well as an assembly guide to build your own.

## **Firmware**

Download the firmware from our master ZMK Firmware Repository: [GCE ZMK Firmware](https://github.com/Grilled-Cheese-Engineering/GCE_ZMK_Firmware_Downloads)

## **KiCad Files**

### Project Files

All of the KiCad files are provided in the the KiCad directory. [KiCad Files](/KiCad/)

Some of the symbols used may not be present. Make sure you have Seeed Studios' XIAO Kicad Symbol Library and ScottoKeebs Kicad Library. 

### Production Files

You can find the JLCPCB production ready files in this directory as well. Just download the zip files in the directory and upload to JLCPCB (or any other fabrication service) to order. [Production Files](/KiCad/production/)

## **3D Printing**

To 3D print the case, use the provided 3MF files in the 3D Printing directory. [3D Printing](/3DPrinting/)

![Picture of the Macropad with the Case](/images/macropad_with_case.png)

# Bill of Materials

### **Equipment**

- Soldering Iron
- Solder
- SMD Soldering Equipment (read note)
    - The Microncontroller Unit is the only surface mount component in this build. While it likely can be hand soldered with a regular soldering iron, the battery pads are inaccesible to a soldering iron.

### **Required Parts**
- (x1) Macro Board PCB
- (x1) Seeed Studio XIAO nRF52840
- (x9) 1N4148 IN4148 Diode DO-35
- (x9) Standard MX Keyboard Switches
- (x1) EC11 Rotary Encoder (With pushbutton)

### **Optional Parts**
- (x1) 1k Ohm Through Hole Resistor
- (x1) 3mm Led (Any color)
- (x1) Lipo Battery* (Any capacity)

*In our testing, a 600mah battery lasts about 7-9 days using bluetooth.

# Build Instructions

Building the macro pad is very straightforward as long as you do things in the right order.

## **1. Solder the MCU to the Board**

Solder the Seeed Studio XIAO board to the pads on the top-left corner of the pcb. The USB-C port should be facing outwards. It is recommended to use an SMD soldering technique such as reflow soldering for this step so the battery pads can be soldered but hand soldering also works at the expense of not having a battery.

> **WARNING:** If soldering the battery pads to the PCB, use less solder paste than you think. It is very easy to bridge the pads and if that happens you will have to desolder the MCU. Trust me, I've had that happen everytime I build one.

## **2. Check the Solder Joints**

Use a multimeter to check for continuity between pins. It is important that there is no bridging between any of the pads. Here is a picture from the schematic showing what pads connect to what parts of the PCB: [Wiring Diagram](images/macropad_wiring_schematic.png). If ANY pads are bridged you will need to fix them. There should not be continuity between the battery positive and negative holes on the board.

## **3. (Optional) Solder the Power LED**

Solder an LED of your choice to the site marked LED. The square pad should be connected to the anode of the LED. Also solder preferably a 1k Ohm Resistor into the site marked R1. Plug in the board to power and the LED should light up. Make sure to snip the leads after doing so.

## **4. Solder the Diodes**

Next solder the diodes to the board. It is recommended to solder them to the front face of the board. Use the reference on the back of the board to get the correct polarity. Snip the leads close to the board once finished.

## **5. Solder the Mechanical Switches**

Now solder the MX Keyswitches onto the front face of the board. If the switch does not have stabilizers built in, it will be challenging to keep the switches straight. The keyplate piece of the 3D printed files can help keep the switches aligned if that is the case.

## **6. Add the Rotary Encoder**

Finally solder the EC11 Rotary Encoder to the PCB on to the front face. It is recommended to solder the mounting pins first to help hold the rotary encoder in place while soldering the other pins.

## **7. (Optional) Solder the Battery**

Solder the your battery to the site marked J1. Be sure that the battery is connected with the correct polarity and the pins are not bridged. The battery was not soldered previously in the guide to protect it from heat from the soldering iron.

## **8. Flash the Firmware**

Flash the firmware to the MCU. If this is the first firmware to be flashed to the device, it should pop up in your file manager automatically. If not, double press the small reset button on the MCU. Finally, drag and drop the uf2 file to the device. It will automatically disconnect and reboot. It may give an error when you drop it onto the device but that is normal.

> You can download the firmware in the Releases Section of this repository: [Firmware Downloads](https://github.com/Grilled-Cheese-Engineering/GCE_ZMK_Firmware_Downloads)

# **Congratulations! You just built the 3x3 Macropad!**

You can use ZMK Studio to customize the keybindings. Please raise an issue if you have any problems with this guide.

-Grilled Cheese Engineering
