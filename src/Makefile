# Project:    StupidPlayer

# Toolflags:
CC           = cc
CCflags      = -c -Otime -depend !Depend -throwback -IC: -APCS 3/32bit/fpe3
Linkflags    = -o StupidPlayer

Files        =	o.common o.dct64 o.dct64_2 o.dct64_4 \
		o.decode o.decode_2to1 o.decode_4to1 \
		o.layer3 o.tabinit o.interface \
		o.main o.soundcode
Libs         = C:o.Stubs OSLib:o.OSLib32

# Final targets:
StupidPlayer:      $(Files) $(Libs)
              link $(Linkflags) $(Files) $(Libs)

#Rule patterns:
VPATH        = @ @.^
.SUFFIXES:    .o .c
.c.o:;        $(CC) $(CCFlags) -o $@ $<

# Dynamic dependencies:
o.layer3: c.layer3 h.mpg123 h.mpglib h.huffman
o.tabinit: c.tabinit h.mpg123
o.interface: c.interface h.mpg123 h.mpglib
o.common: c.common h.mpg123
o.dct64: c.dct64 h.mpg123
o.dct64_2: c.dct64 h.mpg123
o.dct64_4: c.dct64 h.mpg123
o.decode: c.decode h.mpg123
o.decode_2to1: c.decode_2to1 h.mpg123
o.decode_4to1: c.decode_4to1 h.mpg123
o.main: c.main h.mpg123 h.mpglib C:h.kernel
o.soundcode: c.soundcode
