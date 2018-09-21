# Make sure correct Implementation file is selected depending on the board being used 

#include <msp430.h> 
#include <LED.h>


/**
 * main.c
 */
int main(void)
{
	  WDTCTL = WDTPW | WDTHOLD;	// stop watchdog timer
	
 // Simpleblink(); // Blinks an LED on and off repeatedly
    Multiblink(); // Will toggle several LEDs at once
 // Buttonpress(); // flashes LED when button is pressed

	return 0;
}
