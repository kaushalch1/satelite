# Live ysws satelite

## satelite Telemetry and Mission Control System

**Live-X01** is a miniature CubeSat-inspired flight computer and telemetry system built around an ESP32. The project combines real-time sensor monitoring, telemetry logging, system diagnostics, and a dedicated mission-control interface.

The design is intended to look and behave like a small satellite flight computer while remaining practical to prototype and simulate.

---

## Project Overview

Live satelite monitors the satellite's internal systems and displays important telemetry through an OLED interface.

The system can monitor:

- Temperature
- Acceleration and orientation
- Battery voltage
- Storage status
- System status
- Mission status
- Twitch Live stream status

Telemetry can also be stored on a microSD card for later analysis.

---

## Main Features

### Flight Computer

The ESP32 acts as the main flight computer responsible for:

- Sensor communication
- Telemetry processing
- Display control
- Data logging
- Button input
- Status indication
- Mission-state management

### Telemetry Display

The OLED provides a compact mission dashboard.

Example:

```text
CUBESAT-X01
----------------
HACK CLUB LIVE
STREAM: ONLINE

TEMP: 27.4 C
BAT: 82%
IMU: ONLINE
SD: ONLINE

MISSION: ACTIVE

```
##pcb:
<img width="975" height="543" alt="image" src="https://github.com/user-attachments/assets/5374e775-5039-4a42-8125-8302120da982" />
<img width="598" height="693" alt="image" src="https://github.com/user-attachments/assets/1c9bebd0-76bb-489f-8009-38943909d390" />
<img width="1573" height="878" alt="image" src="https://github.com/user-attachments/assets/fcd0f057-752c-4107-8092-3a6eef77a8ca" />
<img width="725" height="567" alt="image" src="https://github.com/user-attachments/assets/80ac2df1-89ea-41f0-a7a6-ca47c026b780" />
<img width="1457" height="183" alt="image" src="https://github.com/user-attachments/assets/6b032a15-0751-4274-8096-beffc9e196bb" />
<img width="1465" height="388" alt="image" src="https://github.com/user-attachments/assets/bb97e59e-ae45-437b-afb0-0769632ed860" />
