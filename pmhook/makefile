#
# This makefile for IBM C Compiler (VAC) will be generate next files:
#
# vncshook.dll
#

NAME    = vncshook
AUTOR   = Andrey Vasilkin
VERSION = 1.0.1
COMMENT = Presentation Manager hook library

DLLFILE = $(NAME).dll
DEFFILE = $(NAME).def

CC      = icc -q -Ss -W1 -O
CCDLL   = $(CC) -Ge- /Gm+

OBJS    = vncshook.obj

.all: $(DLLFILE)

$(DLLFILE): $(OBJS) $(DEFFILE)
  $(CCDLL) $(OBJS) /Fe$(DLLFILE) $(DEFFILE) /b"/ex:1"

$(DEFFILE):
  @echo LIBRARY $(NAME) INITGLOBAL TERMGLOBAL >$@
  @echo EXETYPE OS2 >>$@
  @%%unixroot%%\usr\libexec\bin\date.exe +"DESCRIPTION '@#$(AUTOR):$(VERSION)#@##1## %%F %%T      %%HOSTNAME%%::ru:RUS:::@@$(COMMENT)'" >>$@
  @echo CODE LOADONCALL EXECUTEREAD NOIOPL NONCONFORMING >>$@
  @echo DATA LOADONCALL READWRITE NOIOPL SINGLE SHARED >>$@
  @echo IMPORTS >>$@
  @echo     stKbdPacket = PMWIN.174 >>$@


.c.obj:
  $(CCDLL) -c $*.c

clean:
  @if exist $(DLLFILE) del $(DLLFILE)
  @if exist $(DEFFILE) del $(DEFFILE)
  @if exist *.obj del *.obj
