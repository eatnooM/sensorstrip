# sensorstrip-power-4ir

A board that will take 5V from its USB-C board to and pass it on to all 4 emitters, with an on-off switch.

These boards are ideal if you only ever plan to use the emitters with light guns.

## BOM

| Reference | Part desc / number | Notes |
|----------|-------------|-------|
| J1 | 6-pin SMD Type C connector - [LCSC](https://lcsc.com/product-detail/USB-Connectors_DEALON-USB-TYPE-C-007_C2927027.html) |  |
| J2-J5 | Molex 53261-0271  - [LCSC](https://www.lcsc.com/product-detail/Wire-To-Board-Wire-To-Wire-Connector_MOLEX-532610271_C189700.html) | J2 can be omitted if not daisy chaining |
| - | Picoblade Cable assembly - [Preassembled - Mouser (60cm length)](https://www.mouser.co.uk/ProductDetail/Molex/15134-0206?qs=F%2F1Z9SgJL%252BXkfyBT%252BHsQcw%3D%3D), [LCSC](https://www.lcsc.com/product-detail/_MOLEX-_C293613.html) + (https://www.lcsc.com/product-detail/_MOLEX-_C259763.html) | Need one of these for each emitter board |
| F1 | 0805 PTC - [LCSC](https://www.lcsc.com/product-detail/_Murata-Electronics-_C184863.html) | Overcurrent protection |
| D1 | Status LED - [LCSC](https://www.lcsc.com/product-detail/Light-Emitting-Diodes-LED_Everlight-Elec-19-217-GHC-YR1S2-3T_C72043.html) | Optional |
| R1,R2 | 5.1K 0603 - [LCSC](https://lcsc.com/product-detail/Chip-Resistor-Surface-Mount_PANASONIC-ERJ3EKF5101V_C123727.html) | Required if powering from C-C cable |
| R3 | 1K 0603 - [LCSC](https://www.lcsc.com/product-detail/Chip-Resistor-Surface-Mount_YAGEO-RC0603FR-071KL_C22548.html) | Required for status LED |
| SW1 | DPDT - [LCSC](https://lcsc.com/product-detail/Slide-Switches_C-K-JS202011SCQN_C221666.html) | Optional, but recommended |