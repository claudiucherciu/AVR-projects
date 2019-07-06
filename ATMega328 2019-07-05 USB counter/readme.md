# USB Frequency Counter

This project contains the design and microcontroller code for a USB logging frequency counter. The entire project is open source (open software / open hardware). This project developed from a discussion that started [here](https://github.com/swharden/AVR-projects/issues/1).

![](pcb-3d.png)
![](pcb-wires.png)
![](schematic.png)

## Features
* USB connection allows PC monitoring/logging of frequency
* USB connection not required
  * can be alternatively powered through the 5V pins
  * a SPI-driven 7-segment led module can display frequency
* can use external 10MHz reference
  * don't populate X1, C3, or R14
  * apply 10MHz TTL to the R14 pad
* can use external gate
  * don't populate R8
  * apply 1Hz TTL to the R8 pad
* input signal is amplified and protected (up to 30V)
* no prescaling of input signal
  * every single cycle is counted over extended periods of time
  * cycles not counted in one gate tick roll-over to the next

## Components
* all passives are 0805 (~$1)
* [10MHz 3.3V oscillator](https://www.mouser.com/ProductDetail/Fox/FOX924B-10000?qs=sGAEpiMZZMt8oz%2FHeiymAOqzUXC3weGFrHcwaz7vvYI%3D) ($2.35)
* [SN74LV8154](https://www.mouser.com/ProductDetail/Texas-Instruments/SN74LV8154PWR?qs=sGAEpiMZZMtdY2G%252BSI3N4aQvQNXOTGN6Ghdjz%252BkScFE%3D) ($0.99) TSSOP-20
* [FT230XS-R](https://www.mouser.com/ProductDetail/FTDI/FT230XS-R?qs=sGAEpiMZZMtv%252Bwxsgy%2FhiIaF6qCroMVR1i2pEQA5UpU%3D) ($2.04) SSOP-16
* [ATMega328](https://www.mouser.com/ProductDetail/Microchip-Technology-Atmel/ATMEGA328PB-AU?qs=sGAEpiMZZMvc81WFyF5EdrSRAEYMYvHlMc95YQj%2FArE%3D) ($1.38)
* [mini-USB jack](https://www.mouser.com/ProductDetail/CUI/UJ2-MBH-1-SMT-TR?qs=sGAEpiMZZMu3xu3GWjvQiLfiCTO8RP%252Bk%252BIiwpoT5qew%3D) ($0.49)
* [SMA connector](https://www.mouser.com/ProductDetail/LPRS/SMA-CONNECTOR?qs=sGAEpiMZZMuLQf%252BEuFsOrkd7M7rmHNHidLMZ%2Ftb%252B0T1YCJLScw0qLA%3D%3D) ($1.08)

Total is ~$10

## Changes for Rev2
* simple connection for SPI-driven 7-segment display like [this](https://www.amazon.com/dp/B07CL2YNJQ)
* make PCB smaller
* add mounting screw holes