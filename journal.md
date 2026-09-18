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
# date:18/9
# time spent:1.25hr
## description:
In Blocks 7 through 9, I wrapped up the schematic for my satelite project by adding visual feedback, user controls, reverse-voltage protection, and final power filtering. For Block 7, I integrated a WS2812B addressable RGB LED to serve as the satellite's primary status indicator—hooking up its data input (`DIN`) to GPIO17 and decoupling its 3.3V power supply with a 100nF capacitor. Moving to Block 8, I added an active buzzer on a dedicated GPIO pin for audio alerts alongside four mission push buttons (`UP`, `DOWN`, `SELECT`, `BACK`) wired to GPIO13, GPIO12, GPIO26, and GPIO25 with internal pull-up resistors, giving me full local control over the system's software modes. Finally, in Block 9, I finalized the power stage by adding a Schottky diode in series with the positive input rail to protect against reverse-polarity damage, backed by bulk decoupling capacitors across the 3.3V rail to keep the system's power clean and stable before heading into PCB layout.
## images:
<img width="375" height="320" alt="image" src="https://github.com/user-attachments/assets/e0271251-0e9a-4406-98c0-c008fff41b07" />
<img width="261" height="182" alt="image" src="https://github.com/user-attachments/assets/fd1106e0-28a5-4ca4-bb68-f751363ab40b" />
<img width="325" height="462" alt="image" src="https://github.com/user-attachments/assets/b6134619-5920-4700-8592-35b694c8be34" />
<img width="351" height="337" alt="image" src="https://github.com/user-attachments/assets/364ed664-4e87-41c3-b6c4-5e602dea6924" />

-------
# date:18/9
# time spent:0.75hr
## description:
To clear out the remaining warnings and finalize the schematic, I addressed the Electrical Rules Checker errors by cleaning up dangling elements and resolving electrical pin conflicts.  Then, to fix the persistent "Input pin not driven by any Output pins" errors across the SD card , OLED display , and WS2812B LED , I resolved the pin type mismatch between the ESP32's GPIO pins and the peripheral inputs and adding power flags to explicitly declare the supply rails—KiCad's rule checker properly recognized the signal paths, successfully clearing all 22 violations for a error-free schematic.
## images:
<img width="712" height="672" alt="image" src="https://github.com/user-attachments/assets/7e045ca5-ccf1-4553-8a69-01ce952f5d87" />
<img width="712" height="561" alt="image" src="https://github.com/user-attachments/assets/d6ca0f46-bfb1-4ec6-b912-b603acfa584b" />

-------
# date:18/9
# time spent:0.5hr
## description:
I added the footprints for each part by searching their with their lscs number online and then i had updated the pcb with the schematics
## images:
<img width="1650" height="883" alt="image" src="https://github.com/user-attachments/assets/fc52db08-ed33-4725-a613-614e892f40f7" />
<img width="1561" height="857" alt="image" src="https://github.com/user-attachments/assets/14bbe673-ba5b-43a8-9a9c-7741e93448c4" />


-------
# date:18/9
# time spent:1.75hr
## description:
I routed all the wires in the pcb and also fixed all the drc errors.And checked everything is fine in 3d viewer.in routing i had connected the wires and used vias to move between each layer so that the wires don't get struck in a point.
## images:
<img width="471" height="492" alt="image" src="https://github.com/user-attachments/assets/3823b2be-0917-4d9d-be6b-a3dd6396e3b2" />
<img width="598" height="693" alt="image" src="https://github.com/user-attachments/assets/111c0e3d-5e93-4320-b9e0-03cf69b5ee7e" />
<img width="1573" height="878" alt="image" src="https://github.com/user-attachments/assets/633dec09-9c8e-4324-a305-17f52f72b66a" />

-------

