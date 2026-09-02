# ESP32-C3-Universal-RapidFire-PS4-PS5-Controllers 


Supports:

PS4 Dual Shock: JDM‑001 / 011 / 020 / 030 / 040 / 050 / 055

PS5 Dual Sense: BDM‑010 / 020 / 030 / 040 / 050
How the Mod Detects & Works on ANY PS4/PS5 R2 Trigger
The “Universal” compatibility comes from understanding what the R2 trigger actually is.

Inside every PS4 Dual Shock and PS5 Dual Sense controller, the R2 trigger is not a simple digital on/off switch. It is an analog potentiometer connected to a 3.3V reference line.

The ESP32‑C3 reads this signal as an analog voltage, not a digital state.
This provides two major advantages:

-It works with any potentiometer value used across all PS4/PS5 controller revisions.

-The calibration routine automatically learns your controller’s exact idle and fully‑pressed voltages, ensuring accurate trigger detection regardless of hardware variation.

What the Hardware Mod Actually Does
This is a hardware mod installed inside your PS4 Dual Shock or PS5 Dual Sense controller.
The ESP32‑C3 microcontroller sits between the trigger board and the console, intercepting the R2 signal and providing advanced functionality:

- Rapid‑Fire (continuous or burst modes)

- Button Remapping (map tactile buttons to Square, Triangle, Circle, or X)

- Tactical Assists (Drop Shot, Jump Shot, Auto Reload)

- Macro Playback (up to 6‑step button sequences)

- Randomized Timing to reduce anti‑cheat pattern detection
  
- You configure everything through a web interface hosted on the ESP32's own WiFi access point.


Hardware & Connection

ESP32-C3 Super Mini ✅ Works (cheaper, smaller)
<img width="411" height="537" alt="esp32-c3-super-mini-pinout" src="https://github.com/user-attachments/assets/8b207134-174b-4caf-ba75-2d31c412f810" />
GPIO Mapping (ESP32-C3 Super Mini)
GPIO0- R2 Trigger sense (ADC + Output)
GPIO1- Square button output
GPIO2- Triangle button output
GPIO3- Circle button output
GPIO4- X button output
GPIO5- Tactile Switch A (input)
GPIO8- Onboard Status LED
GPIO10- Tactile Switch B (input)

Need an Easy remap for both controller types.
<img width="1000" height="1000" alt="Easy Remap For Ps5 Controller" src="https://github.com/user-attachments/assets/777e0fc6-fcc5-49d4-ae6a-b43f877f113f" />
<img width="3060" height="4080" alt="Easy Remap For PS4 Controller" src="https://github.com/user-attachments/assets/59bc2e6d-f080-46a8-8ebd-cb565153e6bb" />

PS4 Wiring diagrams:
<img width="1600" height="1600" alt="ESP32-C3 Super Mini Original  Wiring Diagram JDM-040 And JDM-055" src="https://github.com/user-attachments/assets/eb79470f-f4b8-422a-876a-d89911c7d02c" />

<img width="4080" height="3060" alt="JDM-055 Install" src="https://github.com/user-attachments/assets/0e33c8ad-bbf4-483c-8883-722281a39788" />

<img width="4080" height="3060" alt="JDM-055 Install2" src="https://github.com/user-attachments/assets/ea5d5e5a-73b9-492a-9912-cbc2e35cb2b9" />

PS5 Wiring diagrams:

<img width="1785" height="1176" alt="ESP32-C3 Super Mini Original  Wiring Diagram BDM-010 And BDM-020" src="https://github.com/user-attachments/assets/0a4be449-8e09-41e1-9fb8-fdb13dff9a1f" />

Connecting to the Web UI
Power on the ESP32 (it creates a WiFi AP)
Connect your phone/PC to WiFi: RapidFireMod_v0.9.9
Password: 12345678
Open browser → http://192.168.4.1
The themed dashboard loads
<img width="1220" height="1425" alt="ESP32-C3 Universal PS4 And PS5 Controller RapidFire Mod v0 9 9 UI" src="https://github.com/user-attachments/assets/6e8f0618-e23b-48f6-bbe3-76ad730cb68f" />
<img width="1167" height="582" alt="ESP32-C3 Universal PS4 And PS5 Controller RapidFire Mod v0 9 9_UI" src="https://github.com/user-attachments/assets/e6aa8f23-7d78-4946-894a-b2c59cc16738" />

for more details how to use it and what each features do look the Rapid-Fire Mod v0.9.9 — Complete User Guide pdf

[RapidFire Mod v0.9.9 — Complete User Guide.pdf](https://github.com/user-attachments/files/31749242/RapidFire.Mod.v0.9.9.Complete.User.Guide.pdf)

