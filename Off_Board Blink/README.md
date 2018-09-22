// Used multiblink program for offboard led 
// Tried to upload video, but it took up too much data :(

# Readme:

Using the MSP430G2 microcontroller to make an LED blink off board is actually simpler then it sounds. By initially programming the microcontroller with the LED blink code, a connection on the breadboard can be made from the external LED to the GPIO pin corresponding to it. All that is left to get the LED blinking, is to provide power to the processor and its reset pin. To keep the microcontroller from getting damaged, a 1.8 to 3.3 supply voltage should be used. A button can be placed in the circuit path to the reset pin of the MSP430 to switch it on and off. Placing a capacitor in series with the button will limit the time current flows so the LEDs immediately switch off. 


// main.c

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

