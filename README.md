documented pdf can be found here https://drive.google.com/open?id=0BxDy0M91HFancmhxUG1wZmJwaDVSMGd1X0NWRmF4QzdnLWlV
// you will be using atmega 32 and the interrupt values are as follows
prescalar of 128
OCR value 10

 pseudo code as follows- 
 
  TCCR2 |= (1 << CS20) | (1 << CS22) | (1 << WGM21);
	TIMSK |= (1 << OCIE2);
  OCR2 = 10; 

giving u (16 MHz / 128 (prescalar)  / 11 (ocr value) / 8 ) = 1420.45 times cube refreshed per second . (where after 8 interrupts complete 
cube gets refreshed).

note -
please stick to the above interrupt routine values as the base code of cube follows these values.
also in the main function a 3D array has to be made.  for eg in main cube[1][2][5]=1; after execution can go to 1st floor, 2nd flipflop
and 5th led.
display code should be written in ISR  which can check this 3D array made in main and can set its data bits accordingly and
give it to flip flop floor by floor after every interrupt. u can use for loop which updates address decoder 3x8 and inside using
if can check 3D array and determine which all bits to be set high.

also if another meet is required do give me call or meet me live on our drishti irc channel.

IMU READINGS BY KARTIK
GAME CODE BY    AMOLI
DISPLAY CODE BY JAYRAJ
