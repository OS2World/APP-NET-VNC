#
# This makefile for GCC will be generate next files:
#
# ..\bin\kbdxkey.exe
#

# Name for binary (without path and extension)
NAME = kbdxkey

# Binary file extension (dll/exe)
EXT = exe

VERSION = 1.0.0
DESCRIPTION = Keyboard scan utility

# Uncomment next line to make debug version
# DEBUGCODE = YES

# Sources
SRCS = kbdxkey.c namestbl.c testkey.c utils.c pmhelpers.c

# Libraries (-Lpath -lname ...)
LIBS = -L../os2xkey -los2xkey

include ../common/makefile.begin


$(FILE_BIN): msgCompilation $(OBJS) $(FILE_DEF) $(FILE_RES) msgBuilding
	$(CC) $(FILE_DEF) $(LDFLAGS)
	$(LXLITE)
	$(RC) $(RCLFLAGS)

$(FILE_DEF):
ifneq ($(DEBUGCODE),YES)
	@echo NAME $(NAME) windowapi >$@
endif
	@cmd /c %unixroot%\\usr\\libexec\\bin\\date +"DESCRIPTION '@#Andrey Vasilkin:$(VERSION)#@##1## %F               %HOSTNAME%::::::@@$(DESCRIPTION)'" >>$@


include ../common/makefile.end
