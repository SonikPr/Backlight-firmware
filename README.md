# Backlight-firmware
This is the NEON V3 version of the firmware for the backlight AVR microcontroller. This version is compatible with ATmega328P and other Arduino boards.

UPDATE 12/17/2023

Hardware versions:
1. Neon V3.0 
  1602 display, single WS2812b strip, up to 140 diodes
  3x4 keyboard 
  VU meter via 3.5 jack
  Power - ATX power supply, with support for custom fans
  Latest stable version: [5.7.5](https://github.com/SonikPr/Neon-V3-firmware/releases#:~:text=Compare-,NEON%20V3%2C%20ver.%205.7.5,-Latest)
  Scheme - https://www.tinkercad.com/things/gn9lk0HdP5J-neon-v30-w-3x4-and-35-jack?sharecode=FtWyI1e9Bd7sy67PJ4Ts9f0VBa2cvhcvFff83VzBrqw

2. Neon V3.1 
  1602 display, single WS2812b strip, up to 140 diodes
  4x4 keyboard 
  VU meter via 3.5 jack
  Power - USB-C
  Latest stable version: [6.0](https://github.com/SonikPr/Neon-V3-firmware/releases/tag/v.6.0)
  Scheme - https://www.tinkercad.com/things/6VNA8zxZWcT-neon-v31-w-4x4-and-35-jack?sharecode=ebmOwgfFw2_mm0uGv7Oai1tTN8luXRIfmNGmpRaTflg

3. Neon V3.2 
  1602 display, double WS2812b panels, up to 140 diodes
  3x4 keyboard 
  VU meter via 3.5 jack
  Power - USB-C
  Latest stable version: [6.1.1](https://github.com/SonikPr/Neon-V3-firmware/releases/tag/v.6.1.1)
  Scheme - https://www.tinkercad.com/things/6aLX4yF40e0-neon-v32-w-3x4-double-led-panel-and-35-jack?sharecode=7n98JHjzwhS8myhlEonHvaVAOw3xvm8M5qEOJ0Q-3iY





Overview:
Arduino-based NEON V3 controller is a control panel for a programmable LED array, based on WS2812B diodes. Using specially designed diffusers, you can achieve a beautiful neon effect. This board is designed to be powered from a default ATX power supply with an additional PWM-controlled fan. Built-in program hysteresis for the cooling fan is present. On standby control panel can display the clock through internal RTC. 
Controls are presented by a membranous 4x3(4x4 for 3.1) keypad. The graphical interface is present on an LCD 16x2 display. NEON v3 can analyze and visualize music with a microphone or default headphones module. Clipping protection is also present. All preferences (Excluding RTC time) are stored in EEPROM memory and would not be erased in case of power cut. The system is very energy efficient, and power consumption in standby mode is less than 0.1W. Peak power consumption in config (3x59 WS2812B diodes) is 15W.
The system uses two different power lines, 5vSB for the control panel, and 5V default for the LED array.(for Neon 3.0 version)

Newer versions using a single 5v line from Type-c port

Modes:
1. VU meter (with maximum points and default)
2. Plain customizable backlight (HSV color setting)
3. Color shift (HSV values automatically changing through customizable period of time)
4. Rainbow (plain rainbow effect, could go forwards, backward and stay still, color gradient also could be set up)
5. Color breathe (fading and firing up with customizable timings)
6. Plain white (standard white backlight to create pure ambient for work. Triggers MAX brightness)
7. Conference (same as backlight, but uses exact colors to make your face on webcam look natural. Also triggers max brightness)
8. Flame mode (imitating real fire, using Perlin noise. Saw this effect in some AlexGyver videos, ported it to the FastLED library, and added it here)
9. Sleep mode (total shutdown of the strip, but the controller is on standby)
10. Old version has "glitch mode" random strip lagging, and brightness errors, which appear at random times and couldn't be the same every time. Maybe, it would be brought back in the future updates.

Required system components:
1. Arduino nano/uno/mega (AVR microcontroller with at least 2kb of RAM and 32kb of instructions memory. EEPROM presence is not crucial, but without it the system could not be able to store preferences after shutdown.
2. 3x4 keypad (4x4 keyboard)
3. 1602 display with I2C bus adapter
4. MAX9814-based microphone for VU-meter mode (optional), or special adapter for 3.5 jack connection (plain 3.5 port for 3.1 and 3.2)
5. USB connector (for PSU control bus) (Type-c port for 3.1 and 3.2)
6. WS2812b strip
7. ATX power supply (or standard 5V power adapter (minimum 2A for 100 diodes)) (only for 3.0, 5v 2-3A for 3.1 and 3.2) version
