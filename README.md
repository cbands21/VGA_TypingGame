# EC311_FinalProject
Final Project with an FPGA in Digital Logic Design

Typing Turmoil: Escape from Photonics

Carlo Lanza, Ryan Malone, Arnouv Nayana, Frederick Grass

We created a Type Racer game that a player can play until they mistyp any of the words. Following the mistake, the user can view the words per minute with which they typed at. 

https://drive.google.com/file/d/1G5iRECuf5eI2jdjMtPDXkQWsnxvc_WjE/view?usp=sharing

The hierarchy of our code is as follows:

Top.v


PS2Reciever-Takes in data from keyboard coontaining current and last keystrokes, as well as key released or depressed data

key_reciever- Segregates keycode data by use

keycodeDecoder- Converts the 8 bit keystroke into a 5bit character whose bitstream matches that of characters in the  library used by the python script

Debouncer- Scrubs this data to allow for a higher WPM.

SegmentDecoder-Takes in each character and decides which segments should be turned on by the vga controller

vga_controller
The logic for the VGA module is decided by the SegmentDecoder. This decoder is called once per character and decides which of the 16 hard coded boundaries should be filled in.
The VGA driver reads line by line and if the current pixel is in within one of the boundaries that is designated to go high by the SegmentDecoder, that area is colored in.

