PRJ = B-IIS
SRC = main.c uart.c stdio.c shell.c printf.c command.c xmodem.c \
	nand.c IIS.c L3.c
OBJ = $(SRC:.c=.o)

all:	
	armasm start.s
	armcc -c $(SRC)	
	armlink -first start.o -ro-base 0x0 start.o $(OBJ) -o $(PRJ).axf
	fromelf -bin $(PRJ).axf -o $(PRJ).bin
	fromelf -c -d -s $(PRJ).axf -o $(PRJ).txt
	dir *.bin
	
clean:
	del *.o 
	del *.axf
	del *.bin
	del *.txt