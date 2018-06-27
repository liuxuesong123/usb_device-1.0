#include <stdio.h>

#include "system.h"

#include "unistd.h"

#include "alt_types.h"

#include "altera_avalon_pio_regs.h"

alt_u32 LED_TABLE[] = {0xdf,0xbf,0x7f};

int main()

{

 alt_u8 a;

while(1)

{

for(a=0; a<=2; a++)

{

IOWR_ALTERA_AVALON_PIO_DATA(PIO_0_BASE, LED_TABLE[a]);

usleep(50000);

}

}

return 0;

}