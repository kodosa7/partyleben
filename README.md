# partyleben!
## simple party compo system for commodore 64 written in basic

![image](https://github.com/user-attachments/assets/28a33314-f3a9-4160-9840-3ca9fe58b995)

## aim
At FOReVER party, no PC-based party system is being used unlike at other parties.  
This makes the event unique but brings certain complications to the modern technology
world.

Since the FOReVER C64 section never had a similar presentation system like Atari  
and ZX Spectrum sections have, it was at least a little bit disqualifying.

The aim of this program is to bring at least basic (and BASIC) functionailty  
for showing compo entries during the compos.  

The system supports up to 25 entries per compo and can display them in order  
they were stored in, with the pre- and post- compo sequences and previous  
entry name when showing the current entry different than the first one.

## requirements
For use in a compo, two real Commodore 64 machines are required.  
One ``(A)`` to run partyleben!, the second ``(B)`` for running the entries.

Machine ``(A)``: Connect it to the projector (beamer) using appropriate video input.  
This machine doesn't require sound to be connected to the party sound system.

Machine ``(B)``: Connect it to the second projector (beamer) input (if available).  
This machine will be the compomachine, so connect it to the party mix  
and set up the volume levels.

In ideal case, you can use a video switcher to switch between inputs easily,  
e.g. if your beamer doesn't have two suitable video inputs of there's  
complicated to switch the inputs directly on the beamer.  

Having connected both machines to separate preview monitors is very handy.  
Remember, do not face the compomachine ``(B)`` monitor screen to the crowd!

## installation
Just run the ``PARTYLEBEN*`` executable from the D64 disk image.

## additional (not required) actions
- You can prepare your own PETSCII graphics in your favorite editor, just like PETMATE.  
https://nurpax.github.io/petmate/  
- Save it as an ASM file and compile it to address $8000 WITHOUT the BASIC line.  
- Load PARTYLEBEN in an emulator (preferrably VICE https://vice-emu.sourceforge.io/)  
and enter the emulator monitor (alt-M in WinVICE).
- Load your image using command ```l "LOGO" 08 8000``` (name has to be in capital letters)  
- exit the monitor with command '''x'''
- IMPORTANT: perform loading the image each time you change the Basic program length!!!
  (see menu option 3 with instructions)  

## usage
The program is used for a single compo, like the music compo only, graphics compo only, etc...    

1. press ``1`` to edit entries. It will list the BASIC from line ``10000``.
At line 10000, you can change amount of entries for your compo and your componame.  
The number of variable ```a``` must be between 01 and 10, including 0 if there are
less than 10 entries, so e.g. ```a=06```.  
The componame string ```c$``` must be 8 characters long.  

Each entry is represented by one line starting ``<linenumber> e$(x)="        entry name         "``
with centered text,  where ```x``` is the current entry order.  
Edit your entries manually in order they will be presented.
Try to keep the entries text centered.    
DO NOT change the length of the lines. That will destroy the picture in memory.  
Remember to press ``RETURN`` after editing each line to let them store into memory.
Replace dots with spaces in emply lines, if you add text to them.
Keep text in the lines to be centered (add some spaces in the beginning):
- Example:
```10050 e$(6)="          the new compoentry          "```
Leave unused lines intact!

example:
If you have 5 entries in the compo:
```
10000 e$(1)="          compoentry1           "
10010 e$(2)="          compoentry2           "
10020 e$(3)="          compoentry3           "
10030 e$(4)="          compoentry4           "
10040 e$(5)="          compoentry5           "
10050 e$(6)="                                "
10060 e$(7)="                                "
...
```
After finished editing, type ```goto10``` and hit RETURN.  
DO NOT TYPE ```run```! It would destroy the Basic variables.  

2. You can list entries that will be used by pressing ``2``.

3. SAVE the whole program to the disk or D64 image! Like ``SAVE"YOURCOMPONAME",8,1``

4. During the compos, LOAD the corresponding program version you have created for each compo.

5. Start the compo by pressing ``0``. The ``coming up <yourcomponame>`` message appears,
   you're ready to switch this screen to the beamer screen.

Thanks to ```Loki``` for comments and suggestions.  


Pressing ``RETURN`` will advance to the next compo entry.

After reaching the last entry, pressing ``RETURN`` will show ``<yourcomponame> compo end`` message
and then gets you back to the main menu.
