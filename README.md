F2812_PMSM_SVPWM_PID
====================

This is a implementation of Space Vector Pulse Width Modulation(SVPWM) with speed, position and current PID controller for Permanent Magnet Synchronous Motor(PMSM).
By this program, we can control the speed and position of PMSM accurately, which is suitable for industrial control.

This program should excuted on Texas Instrument's DSP TMS320F2812 since some codes are hardware dependant. 
However, if you pay attention to the hardware dependant codes (especially the codes relevent to Event Manager), you can still port this program to other platform ()

main.c                                          
Program entry. Almost all logic is implemented in this file, including SVPWM and PID.

display.c                                     
LED driver program based on BC7281 driver chip. Using to display the speed of motor. 

table.c                                                                 
Since TMS320F2812 is a 32-bit Fixed-point DSP, which means it's powerless when facing Float-point calculation.        
To accelerate the Float-point calculation, we store the results of trigonometric functions at certain interval in this table. Then we can query this table to approximate Float-point calculation.
(Notice: these 3 files contain some Chinese character comments, which may not display properly in your editor or IDE.)

Position.mp4
Shows the position contorl of motor.

Other files: automatic generated by Texas Instrument's Code Composer Studio(CCS) IDE, provide initialization for different hardware module or memory configuration.
