# amit
Description :
It's an Electric Water Heater that I made using AVR ATmega32 chip. It consists of alot of modules such as ADC, EEPROM, SSD (Seven Segment Display), Basic Push Button, Led, Interrupts and the most important is the TIMER. I actually used two timers to calculate time between tasks. The heater uses the EEPROM to save the latest desired temperature the user modified.

The Controller follows the following procedure:

It has the ON/OFF Button that is attached to an external interrupt, that switches between ON and OFF states.
in the OFF state everything is OFF (for sure, lol) and the desired temperature is saved in the EEPROM and the MC is in sleep mode.
in the ON state, the MC sense the actual temperature using the internal ADC and temperature sensor (LM35) and save it to an array.
the array consists of the last 10 readings that are used to make the decision of turning the heater/cooler on and off depending on their average.
the UP and DOWN buttons are to switch from the ON state to the SETTINGS state, where the user can modify desired temperature.
if the user didn't click the UP or DOWN buttons for five seconds, it turns back to the ON state, and the chosen temperature is saved in the EEPROM once again.
The indication led is to know which element (Heater or Cooler) is working and in what state is the controller in.
