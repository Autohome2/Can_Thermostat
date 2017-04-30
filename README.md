# Can_Thermostat
Canbus Home Thermostat and Heating controller System

This project is for a set of modules that connect via a 500K Canbus network. 
They are able to talk directly to one another (peer to peer) or broadcast data for any module to use if it is configured to do so.
The devices use 29bit addressing with a custom higher protocol layed over the std 29bit format.
The device modules are configured via TunerStudio and can either be connected directly or via the master module using passthrough.
Although Tunertudio is normally associated with automotive ECU configuration , the custom ini files written for the devices make strong use of the powerful user interface the this program offers.
You can use either the free version or the full registered product. 
This System is derived from the firmware developed for the Speeduino Gpio project(see my other repositories).
The MCU used are the Teensy 3.2 and the Teensy 3.5 although the use of the STM32 range of devices is under development.Only the flow modules can use a pro-mini with a spi mcp2515 canbus interface
The entire system is wired using CAT5e cable. Two pair carrying the canbus data, with two lots of two pair paralelled up (for increase current capacity) carrying the 24vdc power supply. 
All remote units can either use that power if less han 1A consumption or have their own dedicated supply (as the master and relay devices do)

# What is it?

The system consists of several modules
- 1 - The master. 
- 2 - Room Thermostats
- 3 - Relay controllers
- 4 - flow monitors


#The master Module

This module connects via wifi to the local network which could be accessed over the internet if suitable routing is made in the firewall.
Using passthrough you can connect to other modules on the Canbus Network to adjust parameters or observe data

#The Room thermostats

These have two temperature sensors(DS18B20 devices) one for air temperature the other as a floor probe.
They have two set temperatures one for each sensor channel and two setback temperatures again one for each sensor channel.
The devices have optional 128x64 spi oled displays.
These devices output both to the Canbus and with a digital output to show heat request call.
The paramter setup and data can be viewed either directly or via passthrough over the Canbus with Tunerstudio loaded with the matching ini file
This device is powered by a teensy 3.2, 3.5 or stm32 mcu 

#The Relay Controllers

These devices have no volt contact relay modules.
They can also have local temperature probes
The paramter setup and data can be viewed either directly or via passthrough over the Canbus with Tunerstudio loaded with the matching ini file

#The Flow monitors

These devices read the flow rate of frequency type turbine flow meters and broadcast the data to the network.
they can also have optional temeperature probes.
These devices are either pro-mini , teensy 3.2 or stm32 based