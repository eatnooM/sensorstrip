# sensorstrip

![Image of PCB](resources/sensorstrip-render.png)

License: CC BY-NC 4.0

A replacement sensor bar for use with the Wii with a focus on remaining as slim as possible, with no components on the back of the board to allow mounting directly under a PC monitor: 

![Image of board mounted under a monitor](resources/sensorstrip-mounting.jpg)

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

## Board

Grab the [gerbers](https://github.com/eatnooM/sensorstrip/blob/main/sensorstrip-gerbers.zip) and upload to your favourite PCB fab [Aisler](https://aisler.net/), [OSHPark](https://oshpark.com/), [JLCPCB](https://jlcpcb.com/). Default settings should be fine - I wouldn't recommend getting the boards any thinner than 1.6mm as may restrict your mounting options (the LEDs can fire straight out at 1.6mm without catching on the display because the board is thicker than the LEDs' radius), [as shown here](resources/sensorstrip-pcb-thickness.jpg)

HASL is a-ok to use and the cheapest option, so would recommend this as the surface finish.

## Assembly

### Tools required
- Soldering iron
- Solder (recommend relatively thin solder - this will make it harder to bridge pins by adding too much)
- Flux (will help keep your joints shiny and happy)
- Tweezers (good luck holding 0603 parts in place with your fingers)

Assembly should be possible with just an iron - I'd recommend installing the USB-C port as it's the trickiest and doesn't significantly interfere with installing the resistors.

As this is a _reasonably_ straightforward process, I'll include instructions for those who may be doing SMD soldering for the first time but would of course recommend trying a practice kit as a cheaper and more instructive learning tool first.

### Steps
- Solder the USB connector. If using an iron, I'd tin one of the outer pads and move the port into place while keeping this molten (without lingering too long, of course!) - Once you're happy with the alignment, add a little solder to the other pads. Be sure plenty to get good strong joints on the shielding - these will be providing the bulk of the mechanical strength keeping the port in place. If you bridge any pads, 
- Add the resistors you'll be using. For these, tin a single pad and introduce the component, similar to how you did the USB port, then add solder to the other side. If you're using a tip with significant thermal mass, don't hang about for long; you may melt the solder on the other side _through_ the component. An 0603 resistor will happily float away with the surface tension on your iron and make a new home there.
	- R1 and R4 (120R) are mandatory, as they are used to provide power to the centre LEDs.
	- If using a setup with a full set of 5 LEDs on each side (i.e. including D1, D5, D6, and D10), also populate R2 and R3 (220R)
	- I'd recommend populating R5 and R6 (5.1K) in all cases as they'll allow USB C to C cables to be used, but if this isn't important to you, feel free to omit them.
- Add the LEDs. The LEDs are intended to be soldered through-hole, but instead we'll solder them flat against the board so they stick out of the front. The pad labelled with an A is for the anode (positive) leg, typically denoted by a longer leg. You'll have to trim these to size, so make you keep track of the correct orientation (or figure it out with a multimeter in diode mode, or use a non-clipped LED as reference). I'd recommend bending the legs such that the outer LEDs are angled outwards to increase the range of angles the Wiimote can see the bar from.
- Lastly, add the switch. Handily, orientation does not matter!
