# BoxTurtleMC: BoxTurtle Motor Controller

This is a self sourced DC motor controller for use with [Klipper](https://github.com/ArmoredTurtle/BoxTurtleg) and the  [BoxTurtle](https://klipper3d.org) project. 

![BT_Render](images/PXL_20250323_005901771.jpg)


The main focus is using a BigTreeTech MMB with this controller to enable full BoxTurtle control. It also adds additional support for the "BoxTurtle Lane Controls" mod and the "Project TurtleScreen". This board will also have the option of controlling up to 8 re-spooler motors so it should be useful in large custom BoxTurtle setups. All parts are standard modules available on Amazon. So far the only part not available on Amazon is the CANBUS plug, but this is readily available at [DigiKey.com](https://DigiKey.com). See the photo of the circuit board to see the modules used. Ideally those who go through the process to make circuit boards will make their extras available to others at a minimum cost. I'm selling my extra version 1.0 boards for $7 which is basically cost plus postage. Note the 1.0 board does have a known issue. It has the CANL and CANH pins reversed. Still works, but where klipper wants to use pins 4 and 5 as defaults you have to switch them to 5 then 4. Version 1.1 board will fix this and add some other options. See the attached photo. This will also be an open source project released on github.com. 

# Making a PCB

Download the latest zip files from the 

# BOM

- 1 PCB
- 1 Raspberry Pi Pico or Pico2
- 1-4 DRV8833 DC motor driver modules. 
	1 to 4 as needed. Each provides control for 2 motors each.
- 1 MP1583 power module
- 1 CJMCU-1051 module for CANBUS connectivity
- Socket connectors are optional, but strongly suggested.
	+ 2 2.54mm 20 pin socket connectors for Pi Pico
	+ 1 2.54mm 8 pin socket connectors for CJMCU-1051
	+ 2 2.54mm 6 pin socket connectors for each DRV8833 module.
	+ 2 Molex ???? connectors. 
	+ 2 or more 
	

# Tools Needed
- Basic experience soldering components
- Soldering iron with fine tip
- Good solder. 