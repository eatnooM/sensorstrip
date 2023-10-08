# sensorstrip

![Image of PCBs](resources/sensorstrip-assembled.jpg)

License: CC BY-NC 4.0

An IR LED emitter setup, for use with the Wii or IR-based light guns with a focus on remaining as slim as possible, with no components on the back of the board to allow mounting directly to a display

![Image of board mounted on a TV](resources/sensorstrip-mounting.jpg)

## BOM

| Reference | Part desc / number | Notes |
|----------|-------------|-------|
| J1 (sender) | 6-pin SMD Type C connector - [LCSC](https://lcsc.com/product-detail/USB-Connectors_DEALON-USB-TYPE-C-007_C2927027.html) |  |
| J2 (both), J1 (receiver) | Molex 53261-0271  - [LCSC](https://www.lcsc.com/product-detail/Wire-To-Board-Wire-To-Wire-Connector_MOLEX-532610271_C189700.html) |  |
| - | Picoblade Cable assembly - [Preassembled - Mouser (45cm length)](https://www.mouser.co.uk/ProductDetail/Molex/15134-0205?qs=F%2F1Z9SgJL%252BW0yu3FEJM3cA%3D%3D), [LCSC](https://www.lcsc.com/product-detail/_MOLEX-_C293613.html) + (https://www.lcsc.com/product-detail/_MOLEX-_C259763.html) | |
| D1-3 | IR LED - 940nm - [LCSC](https://lcsc.com/product-detail/Infrared-IR-LEDs_Everlight-Elec-IR204-H60_C60099.html) | 3mm with 2.54mm lead spacing fits well |
| R1 | 7-120R 0805 - [LCSC](https://lcsc.com/product-detail/Chip-Resistor-Surface-Mount_PANASONIC-ERJ3EKF1200V_C169257.html) | Value depends on your LEDs - 56-120R should work with the Everlight emitters |
| F1 | 0805 PTC - [LCSC](https://www.lcsc.com/product-detail/_Murata-Electronics-_C184863.html) | Overcurrent protection |
| R2,R3 | 5.1K 0603 - [LCSC](https://lcsc.com/product-detail/Chip-Resistor-Surface-Mount_PANASONIC-ERJ3EKF5101V_C123727.html) | Required if powering from C-C cable |
| SW1 | DPDT - [LCSC](https://lcsc.com/product-detail/Slide-Switches_C-K-JS202011SCQN_C221666.html) [(alternative)](https://lcsc.com/product-detail/Slide-Switches_XKB-Connectivity-SS-3235S-L1_C500055.html)  | Optional, but recommended; use C&K switch if using bright LEDs |

## Board

Grab the gerbers ([sender](sensorstrip-sender-gerbers.zip), [receiver](sensorstrip-receiver-gerbers.zip)) and upload to your favourite PCB fab ([OSHPark](https://oshpark.com/), [Aisler](https://aisler.net/), [JLCPCB](https://jlcpcb.com/)). Default settings should be fine - I wouldn't recommend getting the boards any thinner than 1.6mm as may restrict your mounting options (the LEDs can fire straight out at 1.6mm without catching on the display because the board is thicker than the LEDs' radius), [as shown here](resources/sensorstrip-pcb-thickness.jpg)

HASL is a-ok to use and generally the cheapest option, so would recommend this as the surface finish.

## Assembly

### Tools required
- Soldering iron
- Solder (recommend relatively thin solder - this will make it easier to avoid bridging pins by adding too much)
- Flux (will help keep your joints shiny and happy)
- Tweezers (good luck holding 0603 parts in place with your fingers)
- Wire crimping tool (if not buying preassembled cables)

Assembly is possible with just an iron. As this is a _reasonably_ straightforward process, I'll include instructions for those who may be doing SMD soldering for the first time but would of course recommend trying a practice kit as a cheaper and more instructive learning tool first.

### Steps - Wii Sensor bar

A typical setup to act as a Wii sensor bar comprises one sender board and one receiver board.

- First, solder the USB connector to J1 onto one board. If using an iron, I'd tin one of the outer pads and move the port into place while keeping this molten (without lingering too long, of course!) - Once you're happy with the alignment, add a little solder to the other pads. Be sure plenty to get good strong joints on the shielding - these will be providing the bulk of the mechanical strength keeping the port in place. If you bridge any pads, try adding some flux and introducing a nice clean iron tip.
- Add the Molex connectors to both boards - J2 on the sender, J1 on the receiver. Similar to the USB port, I've had most success lining up one of the pads, then once aligned properly move onto the mounting points and then the remaining pad.
	- You don't need to populate J2 on a receiver board unless you're connecting additional receivers through it - see the Light gun section.
	- In this revision, receiver boards have swapped polarity between the 'Power in' and 'Power out' Picoblade connectors; this is to ensure you can use the pre-made cable assemblies that do not cross over the wires. If you choose to crimp your own cables, be sure to account for this.
- Add the resistors, and the F1 on the sender board. Tin a single pad and introduce the component, then add solder to the other side. If you're using a tip with significant thermal mass, don't hang about for long; you may melt the solder on the other side _through_ the component. An 0603 resistor will happily float away with the surface tension on your iron and make a new home on it.
	- I'd strongly recommend populating R2 and R3 (5.1K) on the sender board as they'll allow USB C to C cables to be used but if this isn't important to you, feel free to omit them.
- Add the LEDs. The LEDs can be soldered flat against the board so they stick out of the front (recommended when mounting under a display), or through-hole (can help if mounting emitters around the edge of a really thin display). The pad labelled with an A and using a round through-hole pad is for the anode (positive) leg, typically denoted by a longer leg (but not always - shoutouts to the Osram SFH 4547 for keeping us on our toes). You'll have to trim the legs to size, so make you keep track of the correct orientation (or figure it out with a multimeter in diode mode, or use a non-clipped LED as reference). If you're using LEDs with a shallow viewing angle, you may want to angle the outer LEDs slightly to increase effective viewing angles.
- Lastly, add the switch to the sender board. Handily, orientation does not matter!
	- Alternatively, you can bridge the jumper J1 with a blob of solder to force the board to be always on when plugged in. If you anticipate a total power draw over over 600mA, you might want to do this as you'd be exceeding the switch's rating otherwise (300mA per pole - they're both tied together on the PCB).
	
Once you're done, plug in your cable between the Power out of the sender board and the Power in on the receiver anddddd fingers crossed, you have light! The IR LEDs in the BOM aren't visible to the naked eye, so you may want to use a phone to test (I've heard iPhones like to filter IR out, though)

## Considerations - Light Guns 

If you need more emitters, you can daisy chain receiver boards. If you're looking to chain a whopping 8 boards together for a 4x6 setup, however, be aware that the recommended power switch has a 600mA current capacity and the BOM entry for F1 has a hold current of 750mA - the [Littelfuse 0805L100WR](https://www.lcsc.com/product-detail/Resettable-Fuses_Littelfuse-0805L100WR_C80270.html) is more suited for higher draw scenarios.

Aside from the potentially different fuse and LEDs, assembly works just the same as a Wii sensor bar setup, except you will add 2 more power boards with both J1 and J2 populated, so you can pass the power through them to the subsequent board.

With Molex's preassembled cables only running up to 60cm in length, you're unlikely to be able to fit any larger than a 42 inch TV without either crimping your own cables (not fun), ordering a custom cable assembly (I've tried JLCPCB's service and it was pretty good, but delivery is a bit pricey) or using [the coupler board](https://github.com/eatnooM/sensorstrip/blob/main/sensorstrip-coupler-gerbers.zip) to join 2 cables.
You can omit the Molex connectors entirely and just solder wires to feed power through, but be sure the through-hole joints don't mess with your mounting solution (i.e. use thick tape).

## TODO
- Swap jumper footprint for combination SMD / THT to allow for easy power switch relocation
