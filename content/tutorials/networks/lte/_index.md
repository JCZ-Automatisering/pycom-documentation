---
title: "LTE Examples"
aliases:
    - chapter/tutorials/lte
---

The following tutorials demonstrate the use of the LTE CAT-M1 and NB-IoT functionality on cellular enabled Pycom modules.

Our cellular modules support both LTE CAT-M1 and NB-IoT, these are new lower power, long range, cellular protocols. These are not the same as the full version of 2G/3G/LTE supported by cell phones, and require your local carriers to support them. At the time of writing, CAT-M1 and NB-IoT connectivity is not widely available so be sure to check with local carriers if support is available where you are.

Both networks make can make use of the same example:
(Make sure you check the coverage map of your provider to confirm coverage in your area)
```python

from network import LTE
import machine
lte = LTE()
lte.attach(band=20, apn="your apn")
while not lte.isattached()"
    machine.idle()
print("LTE modem attached!")

```
>Note: the first time, it can take a long while to attach to the network. 

If you want to check the status of the modem while attaching, you can use the following commands:
```python
print(lte.send_at_cmd('AT!="showphy"')     # get the PHY status
print(lte.send_at_cmd('AT!="fsm"')         # get the System FSM
```