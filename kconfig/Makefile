CFLAGS  := -I/usr/include/ncurses -DCURSES_LOC="<ncurses.h>" -DLOCALE -Wall -Wmissing-prototypes -Wstrict-prototypes -O2 -fomit-frame-pointer
LDFLAGS := -lncurses

cc := gcc

all : mconf conf

%.o : %.c
	gcc -c $(CFLAGS) -fPIE $(LDFLAGS) $< -o $@

mconf : lxdialog/menubox.o lxdialog/yesno.o lxdialog/textbox.o  \
	lxdialog/inputbox.o lxdialog/util.o lxdialog/checklist.o \
	mconf.o zconf.tab.o
	gcc -o $@ $^ $(LDFLAGS)

conf : lxdialog/menubox.o lxdialog/yesno.o lxdialog/textbox.o  \
	lxdialog/inputbox.o lxdialog/util.o lxdialog/checklist.o \
	conf.o zconf.tab.o
	gcc -o $@ $^ $(LDFLAGS)

clean :
	find -name "*.o" -exec rm "{}" \;

