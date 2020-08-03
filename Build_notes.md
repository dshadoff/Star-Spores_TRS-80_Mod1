# Star-Spores_TRS-80_Mod1 - Build Notes

How to build the code in this repository

## Memory Map

Start Addr | End Addr | Module # | Source File | Function
-----------|----------|-----------|-------------|---------
5460H | 549BH | 1 | entry.asm | 
54A0H | 6777H | 2 | main1 ? | 
6780H | 6E3AH | 3 | titlep.asm | 
6E40H | 774DH | 4 | main2 ? | 
7770H | 7FFFH | 5 | data.asm | 

## Background of original code environment

The game was written in Z-80 assembler on a TRS-80 Model I computer with
Level II Basic and a tape drive (but no disk drive).  I had a 48K upgrade
in the computer.

Radio Shack's "EDTASM" Editor/Assembler was used to manage and
assemble the source.  Some data was also prepared by hand, and entered
using TBUG (included with Disk EDTASM), and/or possibly ZBUG (published
in the January 1981 issue of 80 Microcomputing).

As the source code was too large to be assembled as a single source file,
the code was broken into several pieces, with the values of key labels
being tracked by hand, and adjusted in the referencing source modules if
the values were to change.

As these modules were consuming most of the RAM needed in order to
execute an assembly, comments were not able to be kept in the source
code; rather, they were often managed separately. At the conclusion of
development, I made an effort to create a "gold" assembly output on
fanfold paper, notes for creation of the missing data and re-assembly
of the output.

## Code Reconstruction

While I haven't yet found cassettes of the final version of sourcecode (or
ways to properly load them), I was able to find hardcopy output of the final
version and I am reconstructing it ona Windows PC using modern tools.  I'm
sure I invested quite a bit of effort in order to produce this, and when I
found these notes I was genuinely surprised that I had had the foresight to
do so.

The data in this repository is a reconstruction of the notes I archived at the
completion of the game.
 
## How to Build:

You will need a Window PC with zmac installed:

zmac, located at [http://48k.ca/zmac.html](http://48k.ca/zmac.html) is a modern
cross-assembler written specifcially to process Z-80 assembly sources in the
same form as TRS-80 EDTASM, producing output in formats compatible with TRS-80
emulators.

Within the 'src/' directory, the 'make.bat' batch file will build all of the source
files into a 'zout/' subdirectory, as both '.cmd' and '.cas' files.

In order to assemble all of these files into a single loadable output file, a second step
is required: I used a monitor program called 'ZBUG' (from 80 Microcomputing, the
January 1981 issue), on an emulator - trs80gp .

1. While not strictly required, I loaded a preset format into memory before starting,
to resemble the original TRS-80 (cassette version) bootup: starting from location
4F00H, up until 7FFFH, alternating sets of 40H btyes of 'FFH', followed by 40H bytes
of '00H'.

2. Load each of the modules into memory in turn.  There aren't any overlapping areas,
so it shouldn't matter what sequence they are loaded

3. Write out the entire block, from 4F00H to 7FFFH, with an entry address of 5460H,
to cassette.

4. I did a binary comparion against an original cassette I had from the era, and ensured
that my entered source was accurate (applying updates where I had overlooked errors
previously).
