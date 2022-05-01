# Raspberry-Pi-Pico-8-bit-NTSC
An 8 bit color depth NTSC driver running entirely in PIO state machines. Functions for 2D graphics rendering, PWM tones, Pixel plotting, and reading SNES/NES controllers exist on the Pico's main two cores. One state machine generates Vsync & Hsync signals. The other state machine spits out the contents of VRAM with the help of the DMA channel.

Unlike my previous Pico NTSC sketch, this one displays pixels with 8 bits of color depth meaning each pixel can be 255 different colors. This makes it possible to display images in the RGB332 format. But without a video encoder like an AD724 chip it will appear greyscaled. Converting images to RGB332 format can be done with software programs like a python script. 

Video output uses 8 gpio pins for each bit in each pixel and these pins go through a binary weighted resistor DAC that combines the digital bits to an analog voltage for a TV. 

There are 3 demos that can be selected in the program by holding buttons in different combinations on power up. A sprite animation demo with a walking samurai sprite. A ship sprite demo with a "galaga" looking ship. The pong demo displays an image after it was converted to RGB332 format and plays a melody using one of the many Pi Pico PWM channels.  

In order to build this project in Visual Studio you need the pico_sdk cmake file & the pi pico C development setup


Resistor DAC Connections :


SNES Controller Connections : 


PWM Audio Connections : 
