# sensorstrip

![Image of PCB](resources/sensorstrip-render.png)

License: CC BY-NC 4.0

A replacement sensor bar for use with the Wii with a focus on remaining as slim as possible, with no components on the back of the board to allow mounting directly under a PC monitor (TODO: picture of this)

This will work under a TV just fine, but as of this moment the LEDs on either side are closer together than the stock Sensor Bar. This will shorten the effective range to roughly between 60cm-2m (handy for those playing on a cozier setup; probably not ideal for those playing on massive TVs in their livingrooms). If there's enough demand, I may create a wider version. Alternatively, the project is open source - go nuts.

This will of course work on top of a display too, but the bare board will be prone to collecting dust. I have no plans to add a case at this point.

NOTE: This revision is currently untested.

## BOM

| Reference | Part desc / number | Notes |
|----------|-------------|-------|
| J1 | 6-pin SMD Type C connector - [LCSC](https://lcsc.com/product-detail/USB-Connectors_DEALON-USB-TYPE-C-007_C2927027.html) |  |
| D1-10 | IR LED - 940nm - [LCSC](https://lcsc.com/product-detail/Infrared-IR-LEDs_Everlight-Elec-IR204-H60_C60099.html) | 3mm with 2.54mm lead spacing fits well |
| R1,R4 | 120R 0603 - [LCSC](https://lcsc.com/product-detail/Chip-Resistor-Surface-Mount_PANASONIC-ERJ3EKF1200V_C169257.html) | |
| R2,R3 | 220R 0603 - [LCSC](https://lcsc.com/product-detail/Chip-Resistor-Surface-Mount_PANASONIC-ERJ3EKF2200V_C403073.html) | Required if populating D1,5,6,10 |
| R5,R6 | 5.1K 0603 - [LCSC](https://lcsc.com/product-detail/Chip-Resistor-Surface-Mount_PANASONIC-ERJ3EKF5101V_C123727.html) | Required if powering from C-C cable |
| SW1 | DPDT - [LCSC](https://lcsc.com/product-detail/Slide-Switches_C-K-JS202011SCQN_C221666.html) [(alternative)](https://lcsc.com/product-detail/Slide-Switches_XKB-Connectivity-SS-3235S-L1_C500055.html)  | |
