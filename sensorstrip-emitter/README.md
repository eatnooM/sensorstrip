# sensorstrip-emitter

The crux of the project - a small, simple board to hold some IR LEDs. Any build will include at least one of these.

![Image of emitter board](/resources/emitter.jpg)

As well as these, you will need something to supply power. Any of the boards with 'power' in their name can handle this.

## BOM

| Reference | Part desc / number | Notes |
|----------|-------------|-------|
| J1, J2 | Molex 53261-0271  - [Mouser](https://www.lcsc.com/product-detail/Wire-To-Board-Wire-To-Wire-Connector_MOLEX-532610271_C189700.html) | J2 can be omitted if not daisy chaining |
| D1-3 | IR LED - 940nm - [Mouser](https://www.mouser.com/ProductDetail/720-SFH4547) |  |
| R1 | 7-120R 0805 - [Mouser](https://www.mouser.co.uk/ProductDetail/YAGEO/RC0805FR-0710RL?qs=8Y8p%252BasKcI5T5bn0nqNRsw%3D%3D) / [LCSC](https://www.lcsc.com/product-detail/Chip-Resistor-Surface-Mount_YAGEO-RC0805FR-0710RL_C96347.html)  | Value depends on your LEDs - 7-10R work well with SFH-4547 |
