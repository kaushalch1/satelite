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
# date:18/9
# time spent:1.25hr
## description:
In Blocks 4 through 6, I built out the environmental logging, flight data storage, and power monitoring capabilities for my CUBESAT-X schematic in KiCad. I started in Block 4 by wiring up the DS18B20 digital temperature sensor—giving it 3.3V power, placing a 100nF bypass capacitor across its power lines, pulling its DQ pin high to 3.3V with a 4.7kΩ resistor, and routing the data signal straight to GPIO16. For Block 5, I integrated the microSD card socket to act as the satellite's onboard telemetry logger, connecting its SPI lines  while leaving the unused data pins unconnected. Finally, in Block 6, I added a battery monitoring circuit using a 100kΩ voltage divider connected to VBAT, which scales the battery voltage in half and feeds it into the ESP32's ADC on GPIO35, backed by a 100nF filter capacitor to keep the analog readings smooth and noise-free.
## images:
<img width="462" height="447" alt="image" src="https://github.com/user-attachments/assets/6d866714-6999-4835-8aad-b95bbeb8acfb" />
<img width="822" height="597" alt="image" src="https://github.com/user-attachments/assets/23ff5c3b-70e6-4288-87f5-aaa50512b42a" />
<img width="257" height="395" alt="image" src="https://github.com/user-attachments/assets/ae0a00aa-e0f1-438d-91d4-b0774a0932c4" />

-------
