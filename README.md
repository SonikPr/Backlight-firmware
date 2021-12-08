# Backlight-firmware
This is the 0612 version of the firmware for the backlight AVR microcontroller. This is made by SonikPr, inspired by AlexGyver (https://github.com/AlexGyver). This version is compatible with ATmega328P and other Arduino boards.


The version 0612 is designed for graphical interface hardware version. Max amount of WS2812b diodes for this version is 99 pieces. Version for keyboard only is outdated, but supports higher amount of diodes.

Controls:
1. On default mode use keys 1-8 to set the backlight mode, the changes will dilplay on the strip and on the screen (optional)
2. Press 0 to measure and correct the noise level for VU meter mode (requires AUX or microphone line bus present)
3. Press "#" to open the main menu. Its interface will display on the screen (optional), or the "L" onboard diode will go ON.
4. Navigate through menu using "2" for "Up" and "8" for "Down" keys. Menu tabs is looped, so you can jump to the last tab just clcking "up" on the first tab. To confirm your choice, press "5"
5. Changing system preferences made by clicking "1/4/7" keys to decrease the values and "3/6/9" to increase the values. To go back, you need to press "*".

Modes:
1. VU meter (with maxes and clear)
2. Plain costumizable backlight (HSV color setting)
3. Color shift (HSV values automatically changing through costumizable period of time)
4. Rainbow (plain rainbow effect, could go forwards, backwards and stay still, color gradient also could be set up)
5. Color breathe (fading and firing up with costumizable timings)
6. Plain white (standart white backlight to create pure abmient for work. Triggers MAX brightness)
7. Conference (same as backlight, but uses exact colors to make your face on webcam look natural. Also triggers max brightness)
8. Flame mode (imitating real fire, using Perlin noise. This effect was made by AlexGyver, I only included it to this project)
9. Sleep mode (total shutdown of the strip, but the controller is standby)
10. Ambient sleep (Firing up corner diodes to create low-light ambient for the night (like a nightlamp) (toggles by pressing "*" in sleep mode active)
11. Night light (firing up the strip with reduced white light) (toggles by pressing "*" in sleep mode active)
12. Old version has "glitch mode" random strip lagging, brightness errors, which appears in random time and couldnt be the same everytime. Maybe, it would be brought back in the future updates.

Required system components:
1. Arduino nano/uno/mega (AVR microcontroller with at least 2kb of RAM and 32kb of instructions memory. EEPROM presence is not crucial, but without it the system could not be able to store preferences after shutdown.
2. 3x4 keypad 
3. 1602 display with I2C bus adapter
4. MAX9814-based microphone for VU-meter mode (optional)
5. 5.5x2.5 connector
6. WS2812b strip
7. 5V power adapter (minimum 2A for 100 diodes)
