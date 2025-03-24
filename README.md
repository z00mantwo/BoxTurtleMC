# BoxTurtleMC: BoxTurtle Motor Controller
This is a self sourced DC motor controller for use with [Klipper](https://github.com/ArmoredTurtle/BoxTurtleg) and the  [BoxTurtle](https://klipper3d.org) project. 

![BT_Render](images/MC-Render.png)

The main focus is combining this project with a BigTreeTech MMB. This to enable full BoxTurtle control of the DC motor powered re-spoolers. It also adds additional support for the "BoxTurtle Lane Controls" mod and [Project TurtleScreen](https://github.com/sbtoonz/TurtleScreen). This board will also have the option of controlling up to 8 re-spooler motors so it should be useful in larger custom BoxTurtle setups with more than 4 lanes. 

# Making a PCB
![BT_Render](images/PCB_Editor.png) 

Download the latest zip files from the gerber folder. This file can then be submitted to one of the PCB manufactures online like [PCBWay.com](https://www.pcbway.com/) or [JLCPcb.com](https://jlcpcb.com/). Orders are usually a minimum of 5 PCBs per order and should be around $30 USD including shipping.

Ideally those who go through the process to make circuit boards will make their extra boards available to others at a minimum cost. 

# BOM
All parts are available on Amazon with the exception of the 2 CANBUS plus.
Those are available at [DigiKey.com](https://DigiKey.com).  

- 1 PCB.
- 1 Raspberry Pi Pico or Pico2.
- 1 [1N5817 Diode](https://www.amazon.com/s?k=1N5817+Diode).
- 1 through hole 120 Ohm axial resister.
- 2 2pin [2.54mm Pitch Single Row Pin Header](https://www.amazon.com/s?k=2.54mm+Pitch+Single+Row+Pin+Header)
- 1-4 [DRV8833 DC Motor Driver Controller Board 1.5A Dual H Bridge](https://www.amazon.com/s?k=DRV8833+DC+Motor+Driver+Controller+Board+3A+Dual+H+Bridge) modules.
	1 to 4 as needed. Each provides control for 2 motors each.
- 1 [MP1583EN DC-DC buck converter](https://www.amazon.com/s?k=MP1583EN+dc-dc+5v+buck+converter). A fixed 5V module is suggested.
- 1 [CJMCU-1051](https://www.amazon.com/s?k=CJMCU-1051) module for CANBUS connectivity.
- [2.54mm female pin headers](https://www.amazon.com/s?k=2.54mm+Female+Pin+Header) are optional, but strongly suggested. This allows swapping out components if there is an issue.
	+ 2 2.54mm 20 pin socket connectors for Pi Pico
	+ 1 2.54mm 8 pin socket connectors for CJMCU-1051
	+ 2 2.54mm 6 pin socket connectors for each DRV8833 module.
- 2 [Molex Micro-Fit 3.0 43045](https://www.digikey.com/en/products/detail/molex/0430450414/252509) connectors. Available from DigiKey.com.
- 2 or more [JST XH 2.54mm 2-pin female sockets](https://www.amazon.com/s?k=JST-XH+2.54mm+2pin+female+sockets). This depends on what parts of the board you will make use of.

# Tools Needed
- Basic experience soldering components
- Soldering iron with fine tip
- Good solder. 

# Assembling PCB

Solder on the 2 CANBUS plugs and the MP1583EN module. If you didn't get a fixed 5V MP1583EN then make sure to set it to 5V. You can do this by connecting the board to a CANBUS connection and adjusting the potentiometer on the MP1583EN while monitoring the output voltage via the 5V connector. Note a fixed 5V MP1583EN is suggested to bypass this step.

Next solder on the socket connectors as needed.

Solder on the 1N5817 diode. If you are not using socket connectors for the Pi Pico you can place the diode on the back of the  board. 

CANBUS terminator if needed.

# Klipper configuration

First step is to put katapult on the Pi Pico. Follow the instructions from the katapult website to install katapult on your klipper host. Available at [https://github.com/Arksine/katapult](https://github.com/Arksine/katapult). 

Configure katapult as shown below.
![BT_Render](images/katapult.png) 

Note if you are using a Pi Pico2 change the "Processor Model" to rp2350.

After configuring and making katapult. Connect your Pi Pico via USB to your klipper host.  

lsusb with button for mode.
Command to burn Pi Pico. 

![BT_Render](images/klipper.png) 

Note if you are using a Pi Pico2 change the "Processor Model" to rp2350.

If all is well there should be a green light on the Pi Pico and a red light on each DRV8833. 

# Options

- USB rather than CANBUS

# Early release 1.0 boards
Note the 1.0 board does have a known issue. The CANL and CANH pins are reversed. Still works, but where katapult and klipper want to use pins 4 and 5 as defaults you have to switch them to 5 then 4. Version 1.1 board fixes this. 

![BT_Render](images/PXL_20250323_015415830.jpg) 