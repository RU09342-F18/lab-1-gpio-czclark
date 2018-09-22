# Readme:

There are three programming steps to making the LED on the chosen MSP430 board to blink. In order to implement these steps though, the correct port/pin numbers that correspond to the LEDs must be found. This can be done using the datasheet. The first step in programming the microcontroller is to enable the pin being used as GPIO with PxSEL (set to zero). Then that pin should be configured as an output by setting PxDIR to 1 for the one bit. The final step is to toggle the LED by switching its pin back and forth in the output register (PxOUT). The easiest way to this, is to use a XOR function that is continuously on a loop. A delay is put in so the blinking can be perceived.


// Make sure correct Implementation file is selected depending on the board being used 

#include <msp430.h> 
#include <LED.h>


/**
 * main.c
 */
int main(void)
{
	  WDTCTL = WDTPW | WDTHOLD;	// stop watchdog timer
	
    Simpleblink(); // Blinks an LED on and off repeatedly
 // Multiblink(); // Will toggle several LEDs at once
 // Buttonpress(); // flashes LED when button is pressed

	return 0;
}
