# VCP: Voltage-controlled panner

Shield: [![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]

This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg

The VCP is a panning module that will take a mono input and split it to a pair of channels, hereafter referred to as 'left' and 'right'. The left/right mix can be controlled either by hand, using the CV pot on the front panel, or via a voltage source in which case the CV pot acts like an attenuator for the incoming signal.

It has other uses too - by only using the right output (R), the module can be made to behave like a somewhat crude, but rather effective, VCA.

## Construction

Construction uses through-hole components _except_ for components F1 and F2, which are 1206 SMD pads. These are used by the current limiting resistors or polyfuses. Polyfuses are recommended (fuses rated up to 100mA should be more than adequate) but ferrites or 22ohm resistors could be substituted instead. Should an over-current situation happen, the SMD components are far easier to replace than their through-hole counterparts.

There are no particular gotchas with regard construction apart from the use of matched transistors in the differential pairs (Q1,Q2 and Q3,Q4). Any small signal NPN transistor (2N2222, 2N3904 etc.) can be used here.

Ideally, the resistors in the legs of the differential pairs (R2/R3 and R12/R13) should be matched, but this is less essential than matched transistors - I find that 1% resistors are good enough; anything tighter is overkill.

The recommended op-amp configuration is TL072/082 for U1 and NE5532 or similar for U2 - this isn't set in stone though, and any dual op-amp which is pin-compatible with the TL0x2 series will work. If you don't have any NE5532s then a pair of TL082s or similar will work quite happily. My own preference is for a pair of TL082s.

## Calibration
There are a couple of ways in which the module can be calibrated, depending on whether or not you have an oscilloscope.

*If you have a scope*:

- Connect a signal of known amplitude to the input and turn the level pot fully clockwise. A VCO is good for this - for best results, use a square-wave output.
- Connect the output of the right-hand channel and move the CV pot to roughly 12 o'clock
- Adjust the trimmer potentiometer until the amplitude of the signal is roughly half that of the input signal eg. if the input signal is 5V p-p, adjust the trimmer until it is 2.5V p-p.

*If you don't have a scope*:

You'll have to calibrate by ear - follow the procedure above, but instead of connecting the RH channel to a scope, connect it to your speaker or mixer. Adjust the trimmer until the output sounds right.

Clearly this is far less accurate than using a scope, but it does the job.

# Usage
The 'accepted' control voltage range is 0-12V - negative voltages will be rejected. If you're using a through-zero oscillator as a modulation source you may find it necessary to add a DC offset such that the CV is always greater than 0V. 

A CV of 0V corresponds to a 'fully left' signal whilst a CV of 12V corresponds to 'fully right' - values within this range correspond to various proportions of the signal going to the left and right outputs. If you've got matched transistors and have calibrated the module correctly, an input CV of 6V should correspond to a 50:50 mix to the left and right channels.
