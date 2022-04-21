/*
* A Door Sensor is connected to bit 1 of port B, and an LED is connected to bit 6 of port C
* A Program to monitor Door Sensor and when it opens, it turns ON LED without changing state of other pins
*/
#include <avr/io.h>
int main(void)
{
    DDRB = DDRB&0b11111101;//fd
    DDRC = DDRC|0b01000000;//40
    while (1)
    {
        if(PINB & 0b00000010)//02
        PORTC = PORTC|0b01000000;//40
        else
        PORTC = PORTC&0b10111111;//bf
    }
return 0;
}
