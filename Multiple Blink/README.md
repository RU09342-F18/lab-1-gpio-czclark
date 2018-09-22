# Readme:

To blink multiple LEDs at once, follows the same steps as the simple blink, but with more pins. The important difference between the two assignments though, is to make the LEDs blink at different frequencies. This can be done in different ways, but I had one LED toggle, then after a delay I had that same LED and another LED toggle at the same time. This made so that the first LED toggled twice as fast. In order to make sure the LEDs are blinking in uniform, make sure the output register bits for each LED are set to zero prior to entering the loop. 

// Make sure correct Implementation file is selected depending on the board being used 

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
