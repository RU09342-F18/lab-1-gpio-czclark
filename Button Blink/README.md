# Readme:

In order to make an LED blink on the MSP development boards in response to a switch, firstly a specific switch has to be configured as an input, and then pullup/pulldown resistor associated with that switch has to be enabled. This can be done by setting the switch's directional register bit to 0, and by using the PxREN command for the resistor. After both the LED and the switch are configured, the bit for the switch can be masked, and depending whether it is "1" or "0", the LED can be flashed on and off. This can be implemented with a conditional if/else statement, using an AND function to clear out everything but the one bit being considered. 

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
 // Multiblink(); // Will toggle several LEDs at once
    Buttonpress(); // flashes LED when button is pressed

	return 0;
}
