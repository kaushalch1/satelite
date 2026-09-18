# date:18/9
# time spent:1.25hr
## description:
Before diving into the KiCad design, i thoroughly researched miniaturized CubeSat architectures and searched online for off-the-shelf, accessible hardware components suitable for an educational satellite build. By analyzing standard 1U satellite subsystems such as On Board Data Handling, Attitude Determination and Control Systems, and environmental sensing selected reliable, low power parts like the ESP32 microcontroller, an OLED telemetry display, and I²C sensors. This research helped map out the exact pin configurations, voltage levels, and filtering requirements needed to turn discrete components into a fully integrated, modular schematic.
-------
# date:18/9
# time spent:1.25hr
## description:
Over the last three blocks, I designed and wired up the core electronics for the satelite project in KiCad. I kicked things off in Block 1 by building out the power setup—wiring the ESP32 to the +3V3 and GND rails, throwing in a couple of parallel decoupling capacitors to clean up power ripple, and placing a 2-pin connector for external power. For Block 2, I hooked up an SSD1306 OLED screen to act as the telemetry display, giving it 3.3V power and tying its I²C lines directly to GPIO21 and GPIO22 on the ESP32. Lastly, in Block 3, I added the MPU-6050 6-axis attitude sensor to track the satellite's orientation. I powered its VDD and VLOGIC lines, grounded AD0, shared the existing I²C bus with the OLED, routed the interrupt pin (INT) over to GPIO34, and placed the exact filtering caps needed on REGOUT- and CPOUT -to keep it stable.
## images:
<img width="385" height="606" alt="image" src="https://github.com/user-attachments/assets/a2212f86-32a3-417b-8691-1d1b2a513356" />
<img width="736" height="645" alt="image" src="https://github.com/user-attachments/assets/d1fe3641-e2b6-4aee-b7c9-9a83764e8957" />


-------
