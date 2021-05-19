# Minimal circuit configuration for ESP32
##  What all can i do?
This is just a minimal setup to run the ESP 32 in a stable environment. This configuration support reset,flash a program and extra circuits could added on this basic config for further jobs.The configuration has got the protection circuits and regulators to nullify the issues that may arise on run.
##  Schematics in EAGLE
![SCHEME_ESP32](/images/esp32_minimal_scheme.png "schematic")
## Theoretical part

### ESP32 WROOM32 pinout diagram
---
![SCHEME_ESP32](/images/esp32-pinout-chip-ESP-WROOM-32.png "schematic")

### GPIO PINs usage 

Pins in ESP32 are marked for several other purposes and some of them can only be used as input/ouput,otherwise used may lead to running issues.They are listed as below*

![SCHEME_ESP32](/images/0001.jpg "pins1")
![SCHEME_ESP32](/images/0002.jpg "pins2")
---
### ESP32 boot selection modes

The state of pins GPIO0 & GPIO2 affect the boot mode of ESP32

In normal boot mode the GPIO0 pin should be high and the value of GPIO2 is not an influencer

| Pins| STATE |
| --- | ----------- |
| EN | HIGH |
| GPIO0 | HIGH |
| GPIO2 | *ignored* |

To enter bootloader mode and flash a program the pin GPIO0 should be LOW on restart(To restart the EN pin needs to be shifted from HIGH TO LOW for a second). The value of GPIO2 pine should be floating/LOW and shouldn't be HIGH

| Pins| STATE |
| --- | ----------- |
| EN | LOW |
| GPIO0 | LOW |
| GPIO2 | LOW/ *unconnected* |


