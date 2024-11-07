# sensorstrip-power-4ir

A board that will take 5V from its USB-C board to and pass it on to all 4 emitters, with an on-off switch.

![Image of power-4ir board](/resources/power-4ir.jpg)
_Old picture - there have been some changes since this picture_

These boards are ideal if you only ever plan to use the emitters with light guns.

## BOM

| Reference | Part desc / number | Notes |
|----------|-------------|-------|
| J1 | 6-pin SMD Type C connector - [Mouser](https://www.mouser.co.uk/ProductDetail/GCT/USB4135-GF-A?qs=Li%252BoUPsLEnt6HRo6RUvaXA%3D%3D) / [LCSC](https://lcsc.com/product-detail/USB-Connectors_DEALON-USB-TYPE-C-007_C2927027.html) |  |
| J2-J5 | Molex 53261-0271  - [Mouser](https://www.mouser.com/ProductDetail/Molex/53261-0271?qs=%252B72YyncTwW%252B8%252BBjraxGf3A%3D%3D) | |
| - | Picoblade Cable assembly - [Preassembled - Mouser (60cm length)](https://www.mouser.com/ProductDetail/Molex/15134-0206?qs=F%2F1Z9SgJL%252BXkfyBT%252BHsQcw%3D%3D) / [LCSC - housing](https://www.lcsc.com/product-detail/_MOLEX-_C293613.html) + [LCSC - terminal](https://www.lcsc.com/product-detail/_MOLEX-_C259763.html) | Need one of these for each emitter board |
| F1 | 0805 PTC - [Mouser](https://www.mouser.com/ProductDetail/Murata-Electronics/PRG21BC0R2MM1RA?qs=makukexe9nzHJ%252Bvxp0S09w%3D%3D) / [LCSC](https://www.lcsc.com/product-detail/_Murata-Electronics-_C184863.html) | Overcurrent protection |
| D1 | Status LED - [Mouser](https://www.mouser.co.uk/ProductDetail/Wurth-Elektronik/150060GS75000?qs=LlUlMxKIyB0UYkq5lDO8nA%3D%3D) / [LCSC](https://www.lcsc.com/product-detail/Light-Emitting-Diodes-LED_Everlight-Elec-19-217-GHC-YR1S2-3T_C72043.html) | Optional |
| R1,R2 | 5.1K 0603 - [Mouser](https://www.mouser.com/ProductDetail/Panasonic/ERJ-3EKF5101V?qs=MVjVSMjNRMqhyossZ5oXsQ%3D%3D) / [LCSC](https://lcsc.com/product-detail/Chip-Resistor-Surface-Mount_PANASONIC-ERJ3EKF5101V_C123727.html) | Required if powering from C-C cable |
| R3 | 1K 0603 - [Mouser](https://www.mouser.co.uk/ProductDetail/Panasonic/ERJ-3EKF1001V?qs=H7k1u0Mp9JTM8yQxOuvoDg%3D%3D) / [LCSC](https://www.lcsc.com/product-detail/Chip-Resistor-Surface-Mount_YAGEO-RC0603FR-071KL_C22548.html) | Required for status LED |
| SW1 | DPDT - [Mouser](https://www.mouser.co.uk/ProductDetail/CK/JS202011SCQN?qs=LgMIjt8LuD95JYWxZ7NvZA%3D%3D) / [LCSC](https://lcsc.com/product-detail/Slide-Switches_C-K-JS202011SCQN_C221666.html) | |
