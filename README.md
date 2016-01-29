README file for vt52 vnc viewer, (c) 1999 Milan Pikula

0. About
1. License
2. Installation & running
3. Bugs & features
4. Contact

0. About

	vt52vnc is a VNC ( http://www.uk.research.att.com/vnc ) viewer,
which can be used on old, green, monochromatic, prehistoric terminals
labeled vdt52s, which are capable of vector graphics. The software is
functional, but incomplete: it does not support compression,
passwords and there are many ways to optimize the output.

1. License

	This software is distributed under the terms of GNU GPL license, see
`COPYING' file.

2. Installation & running

	1) edit Makefile to adjust some parameters,
		vi Makefile
	2) run `make'
		make
	3) optionally install:
		cp vt52vnc /usr/local/bin

3. Bugs & features

	Mouse:

	As vdt52s does not have the mouse or any other pointing device,
one of three unlabeled buttons near the numeric keypad have been used to
act as mouse-lock. When you depress it, you can use the numeric keypad to
move the mouse, and `+', `-', `.', `enter', `0', and `5' as button
1,2,3 toggle and button 1,2,3 click.

	Speed:

	Based on my own experiences, I recommend the speeds 38400 and
higher for "real work". The screen is drawn by rectangles. This is done
to improve the reaction times, when the screen changes very often.

	The software uses the XOR mode to actually draw the image,
which can be improved using AND and OR mode in some cases. One can
also imagine another optimizations for particular shapes. I will not
add those optimizations, as the decisions are very memory-consumptive
and after all, I don't want to implement some kind of prolog just to
choose the right one. If you want to improve it, let me know.

	Colors:

	The monochromatic translation is done by some bit of green
color, which can be changed at the beginning of vncproto.c. If you
want to make it better (implement some dithering or (better) the
shape finding algorithm), let me know.

	Why and how:

	The work was inspired by mine never-ending desire for an X
display on the "frog". Display drawings are based on the graphics
library by Marek Zelem, which is, in turn, based on the documentation
for vdt52s, as my work is based on vnc protocol documentation. Coded,
of course, on vdt52s terminal with wrong Enter and Control. The sources
are written to be easily extended.

4. Contact

	Milan Pikula, <www@terminus.sk> or <www@fornax.sk>

