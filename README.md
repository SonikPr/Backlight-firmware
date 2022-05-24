# Backlight-firmware
This is the NEON V3 version of the firmware for the backlight AVR microcontroller. This version is compatible with ATmega328P and other Arduino boards.


HUGE UPDATE!!!!
Current version is 5.4.7. This version received a lot of new features, new tweaks, options and a lot of optimization

Overview:
Arduino-based NEON V3 controller is a control panel for progreammable LED array, basen on WS2812B diodes. Using specially designed diffusers, you can achieve beautiful neon effect. This board is designed to be powered from default ATX power supply with additional PWM-controlled fan. Built-in program hysteresis for cooling fan is present. On standby control panel can display the clock through internal RTC. 
Controls are presented by membranous 4x3 keypad. Graphical interface is present on LCD 16x2 display. NEON v3 can analyze and visualize music with microphone or deffault headphones module. Clipping protection is also present. All prefereneces (Excluding RTC time) are stored in EEPROM memory and would not be erased in case of powercut. System is very energy efficient, power consumption in standby mode is less than 0.1W. Peak power consumption in config (3x59 WS2812B diodes) is 15W.
System is using two different power lines, 5vSB for control panel, and 5V default for led array.

Modes:
1. VU meter (with maximum points and default)
2. Plain costumizable backlight (HSV color setting)
3. Color shift (HSV values automatically changing through costumizable period of time)
4. Rainbow (plain rainbow effect, could go forwards, backwards and stay still, color gradient also could be set up)
5. Color breathe (fading and firing up with costumizable timings)
6. Plain white (standart white backlight to create pure abmient for work. Triggers MAX brightness)
7. Conference (same as backlight, but uses exact colors to make your face on webcam look natural. Also triggers max brightness)
8. Flame mode (imitating real fire, using Perlin noise. This effect was made by AlexGyver, I only included it to this project)
9. Sleep mode (total shutdown of the strip, but the controller is standby)
10. Old version has "glitch mode" random strip lagging, brightness errors, which appears in random time and couldnt be the same everytime. Maybe, it would be brought back in the future updates.

Required system components:
1. Arduino nano/uno/mega (AVR microcontroller with at least 2kb of RAM and 32kb of instructions memory. EEPROM presence is not crucial, but without it the system could not be able to store preferences after shutdown.
2. 3x4 keypad 
3. 1602 display with I2C bus adapter
4. MAX9814-based microphone for VU-meter mode (optional), or special adapter for 3.5 jack connection
5. USB connectior (for PSU control bus)
6. WS2812b strip
7. ATX power supply (or standard 5V power adapter (minimum 2A for 100 diodes))
