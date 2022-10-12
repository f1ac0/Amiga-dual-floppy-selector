# Amiga dual floppy selector
This is a device to connect two floppy drives inside an Amiga, identify them to the system, then choose which one is the DF0 to boot from. Its main purpose is to connect a physical drive and an emulator, but you can use two physical drives or two emulators if you want.

It proposes four alternatives :
- B=1, A=1 : Physical drive as DF0 only
- B=1, A=0 : Emulator as DF0 only
- B=0, A=1 : Physical drive as DF0 and emulator as DF1
- B=0, A=0 : Emulator as DF0 and physical drive as DF1

In addition :
- It may be plugged directly to the motherboard floppy header, thanks to its small size.
- It has a single connector for a ribbon cable to the floppies. The required ribbon cable IS NOT a standard PC floppy ribbon : see below. You can also use my floppy emulator project that provides an output to daisy chain the other drive.
- There are two inputs, A and B. They can be connected either to a mechanical 2P4T switch, or to the selector output of my floppy emulator project.
- It requires the MTRX and the DRES signals. You may pick them up from the connector or from components on the board.
- Beware that you should not activate an external drive on the DB23 connector using the same id as an internal drive. When an external DF1 is connected, you should use "DF0 only" settings.
- If you permanently use external drives on the DB23 connector, you may wire another DS signal instead of DS1. The device has pin headers for that.


# Disclaimer
This is a hobbyist project, it comes with no warranty and no support. Also remember that the Amiga machines are about 30 years old and may fail because of such hardware expansions.

I publish my work under the CC-BY-NC-SA license. The content of this repository is the result of weeks of work, requiring investment in tools, parts, prototypes, and risky tests on his own equipment. For this reason the author does not want third parties to sell products and keep all the profit, usually without even offering support to their customers. If you see people selling this without the consent of the author, don't buy from them.

If you find it useful and want to reward me : I am always looking for Amiga/Amstrad CPC hardware to repair and hack, please contact me.

# BOM
- 1x 74HCT153D
- 1x 74HCT74D
- 1x 74HC03D
- 3x 100nF 0805 capacitors
- 3x 10k 0805 resistors
- 1x 2x17 pins socket. Remove pin 3 which is a key.
- 1x 2x17 pins header. Remove pin 3 which is a key.
- floppy power connectors or wires. You may use a 1x4 angled pin header, and two female floppy power connectors taken from an old PSU.
- pin headers or wires for DRES signal, MTRX signal, A and B selector, DS0 and DS1 jumpers.
- a 2P4T switch or my floppy emulator project

# Making it
Components are SMD, but have large pin pitch. They are not hard to solder.

Check for shorts at least between 5V, 12V and GND traces before applying power !

Use a 3 connector ribbon to connect both drives. Warning this is not a standard PC ribbon ! You can modify a PC floppy ribbon, the twist need to be changed :
- the cable is straight between the adaptor and the first connector (to the emulator),
- twist both 10-12 and 14-16 before the second connector (to the physical drive).

To connect the wires to components on the motherboard, here is a tip :
- Take a metal pin from the female 2.54mm pin socket, which is shaped as a lyra. The one you removed from pin 3 for example.
- Solder the wire on the pin, where you normally solder it.
- Place the pin inside heat-shrink tube, with only 1mm of metal uncovered from the tips of the lyra.
- Snap the tip on the lyra on the component where you want to connect.

# Using it
- Connect the device to the floppy header on the motherboard
- If you choose to use DF0 and DF1 from the floppy connector, install jumpers on S0 and S1 (you may install the jumpers 90° to exchange the drive numbers). Otherwise, connect the square pads to the required signals.
- Connect the DRES and MTRX signals : for example DRES on U37 pin 8, and MTRX on U36 pin 2
- Connect the ribbon to the drives
- Connect the power cable from the motherboard
- Connect the power cables to the drives
- Select the required configuration on the switch
- Turn on the Amiga

