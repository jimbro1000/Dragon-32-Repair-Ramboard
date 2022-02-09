# Dragon32 Repair Ramboard
Plugin ram board for Dragon 32 Mk2 Issue 6, to replace 4116 chips with 4164

## State of Design
This is an _alpha design_, yet to be tested. **Use at your own risk!**

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

If you have an earlier D32 or a D64 (or one of the variants), this will **not**
fit. The design can be adapted to work but not in the current form.

## Assembly
1. Fit two rows of long pin headers for IC1 and IC43 to the underside of the 
board, these are the left hand biased pads of each socket pair
2. Fit pin headers for pin 2 and pin 14 for each of the remaining IC positions 
on the underside of the board
3. Trim the soldered pin headers down on the top side of the board to allow 
clearance for the sockets
4. Fit 16 dip-16 sockets in the U1 to U16 positions on the top side of the board, 
these are the right hand of each socket pair (once fitted you should see a single 
column of pads between each socket). Trimming of the sockets may be necessary if 
the fitted pin headers are too high on the top side of the board
5. (optional) fit the 1k resistor and led (shows a live 5v connection to the 
board)
6. (experimental) Fit decoupling capacitors to positions C1-C16. If the positions
are not filled then the pads must be bridged to provide Vcc 5V to the onboard
memory chips (U1-U16)

tip: If you fit the sockets to the main board first, these can be used to make 
sure the header pins align correctly before soldering them in. Care must be taken
to ensure alignment and position is correct and that stray solder splashes are not
left on the main board

## Fitting
1. remove (desolder) all 16 memory chips from the board
2. fit 16 dip-16 sockets in the positions left vacant by the memory chips
3. fit the repair board making sure that the pins line up correctly

note: only IC1 and IC43 have a significant number of pins and cannot
easily be misaligned. Only 2 pins should be fitted for the remaining
sockets for the Din and Dout pin positions

## BoM
| Item | Quantity | Positions |
|:-----|:--------:|:----------|
| dip-16 socket | 16 | U1-U16 |
| dip-16 socket | 16 | IC1-IC8, IC36-IC43 (main Dragon board) |
| pin header | | U1, U16 fully populated |
| pin header | | U2-U15 pin 2, pin 14 |
| red led 5mm | 1 | (optional) D1 |
| 1k 0.25W resistor | 1 | (optional) R1 |
| 330nF capacitor | 16 | (experimental) C1-C16 |

## Contact
The project was created by Julian Brown.
Use the Facebook "Dragon 32/64 Owners/Users" group for contact