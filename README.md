# sensorstrip

![Image of PCB](resources/sensorstrip-render.png)

License: CC BY-NC 4.0

NOTE: This revision is currently untested.

A replacement sensor bar for use with the Wii with a focus on remaining as slim as possible, with no components using the back of the board to allow mounting directly under a display (TODO: picture of this)

## BOM

| Reference | Part desc / number | Notes |
|----------|-------------|-------|
| J1 | 6-pin SMD Type C connector - [LCSC](https://lcsc.com/product-detail/USB-Connectors_DEALON-USB-TYPE-C-007_C2927027.html) |  |
| D1-10 | IR LED - 940nm - [LCSC](https://lcsc.com/product-detail/Infrared-IR-LEDs_Everlight-Elec-IR204-H60_C60099.html) | 3mm with 2.54mm lead spacing fits well |
| R1,R4 | 120R 0603 - [LCSC](https://lcsc.com/product-detail/Chip-Resistor-Surface-Mount_PANASONIC-ERJ3EKF1200V_C169257.html) | |
| R2,R3 | 220R 0603 - [LCSC](https://lcsc.com/product-detail/Chip-Resistor-Surface-Mount_PANASONIC-ERJ3EKF2200V_C403073.html) | Required if populating D1,5,6,10 |
| R5,R6 | 5.1K 0603 - [LCSC](https://lcsc.com/product-detail/Chip-Resistor-Surface-Mount_PANASONIC-ERJ3EKF5101V_C123727.html) | Required if powering from C-C cable |
| SW1 | DPDT [LCSC](https://lcsc.com/product-detail/Slide-Switches_C-K-JS202011SCQN_C221666.html) [(alternative)](https://lcsc.com/product-detail/Slide-Switches_XKB-Connectivity-SS-3235S-L1_C500055.html)  | |
