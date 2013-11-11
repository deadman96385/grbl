#A fork of Grbl for Sanguinololu
------------

grbl is a really nice piece of software, but the available grbl shields for Arduino are 
difficult to get, and quite pricey. 

RepRap controller boards on the other hand can be had for dirt cheap,
offer all the required features- at least 3 stepper controllers, 
inputs for endstops and buttons and even a few power FETs which 
can be repurposed for coolant control or maybe even ATC. They usually use AVR microcontrollers 
with more RAM and flash, compared to 328p which is the default target for grbl.


This fork allows grbl to be run on Sanguinololu- it's tested and known to be working on Sanguinololu 1.4 on my mill. 
With a few changes to pin_map.h, it should run on other versions of RepRap controllers.


The need for this fork stems from the fact that grbl assumes that step and direction signals
for all axis are located on a single AVR port. That allows some clever optimizations when
multiple axes are moving simultaneously.

Unfortunately, none of the RepRap controller boards have these signals on single port. The same 
goes for limit switch inputs.
