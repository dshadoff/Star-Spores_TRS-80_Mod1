# Star-Spores_TRS-80_Mod1
Repository of information from development of Star Spores assembly-language game for the TRS-80 Model I computer in 1982

## Background

In 1980, I got my first computer and within about 2 months, I felt I had
outgrown BASIC and moved on to assembler, and loved the speed that it
provided.

I also really enjoyed the videogames in the burgeoning arcade industry,
stepping into an arcade every chance I was near one, just to check out
the new games, and spend a few quarters (I didn't have enough money or
time to get very good at the games).

Meanwhile, some of the arcade feel was made available to the TRS-80
by Big Five Software and their line of games, which was excellent and
an inspiration to people like myself - to know that the machine was ever
capable of this !

## Original Tools

Star Spores was programmed over the summer of 1982, and although I
solicited several publishers to market the game, it wasn't ultimately
licensed.

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
of the output.  I'm sure I invested quite a bit of effort in order to
produce this, and when I found these notes I was genuinely surprised
that I had had the foresight to do so.

## Recompiling

While I haven't yet found cassettes of the final version of sourcecode (or
ways to properly load them), I was able to find hardcopy output of the final
version and I am reconstructing it here using modern tools.

zmac, located at [http://48k.ca/zmac.html](http://48k.ca/zmac.html) is a modern
cross-assembler written specifcially to process Z-80 assembly sources in the
same form as TRS-80 EDTASM, producing output in formats compatible with TRS-80
emulators.

## Organization

Sources and re-compilation information can be found in the 'src/' subdirectory, and
miscellaneous other development notes can be found in the 'notes/' subdirectory.
When a compiled version can be reliably output, this will be in a 'release/'
subdirectory.

