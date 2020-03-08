# Log: Anycubic Delta Linear Plus

## Replace A4988 with TMC2209 (v3.0)

Stock voltages of the A4988 drivers in volt:
|  X  |  Y  |  Z1  |  E0  |  E1  |
| ---|----|---|---|---|
| 0.822 | 0.839 | 0.848 | 0.828 | 0.9 |

* Set all TMC2209 to 0.9V
* Short RX and TX
* Isolate/remove SP Pin (required to get Stealth Chop running in UART mode on an MKS Gen L board, I left it at that.)
* Marlin: set drivers in Marlin to `TMC2209_standalone`
* Marlin: reverse direction

## Calibration / Levelling

After auto-calibration/-levelling, the noozle is too low and scratches the bed. Setting the Z-Probe Height to 15.6 mm instead of the default 16.8 mm produces a *tolerable* 1st layer (TODO: proper levelling, bed mount/brackets). 

Levelling doesn't seem to work. The bed is slightly warped (concave). After using auto-calibration and -levelling and adjusting Z-Probe Height to prevent the noozle crashing into the bed at z=0, only the center of the bed is useable. For other areas the noozle is too close, Squishing the 1st layer too flat, if allowing for extrution at all. It looks as if the bed levelling doesn't have any effect at all. 
