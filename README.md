# Dragon32 Repair Ramboard
Plugin ram board for Dragon 32 Mk2 Issue 6, to replace 4116 chips with 4164 or 41256 chips

## State of Design
This is an _pre-release design_, yet to be fully tested. **Use at your own risk!**
The current version is v1.0.1 and has passed basic testing only

## Purpose
This project defines a hardware solution for replacing faulty 4116 16kx1bit
memory chips with the cheaper, more reliable 4164 64kx1bit design.

The aim is to minimise complexity of repair by providing a single plug-in
board with 16 socketed 4164 chips. To plug the 4164 chips in directly to
the Dragon board requires modifications to the chips due to slight
incompatibilities.

## Compatibility (read carefully)
The current design will **only** work with the Dragon 32 Mk2 Issue 6 
mainboard with 16 4116 chips. There are many variants of the mainboard so 
double check that the it is the right design.

To confirm it is correct there should a row of 9 chips across the top right
of the board (IC1-IC8 and IC43), a further row of 7 chips should be underneath 
it (IC36-IC42).

The board has two jumpers (JP1 and JP2) to allow configuration of how pin 1 of
the replacement memory chips is handled. By default the jumpers are bridged to
supply 5v to pin 1 for better compatibility with 4164 chips. Most will allow a
low or high signal but some demand that the pin is at 5v.

If you are using 41256 chips or suitable 4164 chips that jumper position can be
modified by cutting the bridge and soldering to the ground side of the jumper.
This facilitates the use of half-good chips (provided the same half is consistent
for each bank).

**Important:**
If you have an earlier D32 or a D64 (or one of the variants), this will _**not**_
fit. The design can be adapted to work but not in the current form.

## Ordering Boards ##
The design of the board is in Kicad 6 - I have not generated gerber files
for the pre-release. You will need to download this repository and open 
the files in a compatible package.

I've ordered early prototype boards from PCBWay and they work out at
approximately £22 for 10 boards (ordering less will not save any money
and just makes the individual boards more costly).

## Assembly
1. Fit two rows of long pin headers for IC1, IC36 and IC43 to the underside of the 
board, these are the left hand biased pads of each socket pair. Make the projection 
above the board as small as possible - some pin headers will allow the plastic 
spacer to slide (especially when warmed)
2. Fit pin headers for pin 2 and pin 14 for each of the remaining IC positions on 
the underside of the board. Make the projection above the board as small as possible
3. Trim the soldered pin headers down on the top side of the board to allow 
better clearance for the sockets
4. Check the JP1 and JP2 bridge positions are as desired, once the sockets are 
fitted it can be very tricky to modify the bridge
5. Fit 16 dip-16 sockets in the U1 to U16 positions on the top side of the board, 
these are the right hand of each socket pair (once fitted you should see a single 
column of pads between each socket). Trimming of the sockets may be necessary if 
the fitted pin headers are too high on the top side of the board. From experience 
applying pressure to the sockets will allow them to flatten against the board...
6. (optional) fit the 1k resistor and led (shows a live 5v connection to the 
board)
7. (optional) fit a 2-pin header on Vcheck for monitoring the voltage supplied to
the board

tip: If you fit the sockets to the main board first, these can be used to make 
sure the header pins align correctly before soldering them in. Care must be taken
to ensure alignment and position is correct and that stray solder splashes are not
left on the main board.

tip: If you have ordered multiple boards, use a blank board as a guide to keep the pins
tightly aligned to the correct pattern. 

## Fitting
1. remove (desolder) all 16 memory chips from the board
2. fit 16 dip-16 sockets in the positions left vacant by the memory chips
3. fit the repair board making sure that the pins line up correctly

note: only IC1, IC36 and IC43 have a significant number of pins and cannot
easily be misaligned. Only 2 pins should be fitted for the remaining
sockets for the Din and Dout pin positions

## BoM
| Item | Quantity | Positions |
|:-----|:--------:|:----------|
| dip-16 socket | 16 | U1-U16 |
| dip-16 socket | 16 | (recommended) IC1-IC8, IC36-IC43 (main Dragon board) |
| pin header 8x1 | | IC1, IC36, IC43 fully populated |
| pin header 1x1 | | IC2-IC8, IC37-IC42 pin 2, pin 14 |
| red led 5mm | 1 | (optional) D1 |
| 1k 0.25W resistor | 1 | (optional) R1 |
| pin header 2x1 | 1 | (optional) Vcheck1 |

## Contact
The project was created by Julian Brown.
Use the Facebook "Dragon 32/64 Owners/Users" group for contact