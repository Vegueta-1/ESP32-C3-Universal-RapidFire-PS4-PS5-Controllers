<img width="2112" height="480" alt="vegueta1 1280x300 pixels" src="https://github.com/user-attachments/assets/8723e096-4ea4-4511-8fd0-d55f2a77515d" />

ESP32‑C3 Universal RapidFire & Remap — Update Log Version 0.9.11

Web App Improvements

-Improved stability of the onboard WebConfig interface used for mode switching, remap editing, and macro configuration.

-Hardened internal routing to prevent session drops during configuration changes.

-Added English / Spanish language toggle accessible from the ES/EN icon in the Web UI.
 
-Language preference is automatically saved and restored using browser localStorage.


Sleep / Wake Reliability Fixes

-Fixed GPIO state handling during deep sleep and wake-up cycles.

-Startup routine now releases any leftover GPIO holds before Wi-Fi AP initialization.

-Button output pins are safely configured as INPUT_PULLUP during initialization to prevent unintended states.

-Ensures native controller functionality remains fully operational while the ESP32-C3 is asleep.

-Improves wake reliability and prevents button lockup conditions after sleep cycles.

Stability & Reliability

-Improved overall firmware robustness during WebConfig interaction and power state transitions.

-Reduced risk of unexpected controller behavior caused by GPIO retention after wake-up.

-Enhanced long-term operational stability for both PS4 DualShock and PS5 DualSense installations.

-Added support for Seeed Studio Xiao ESP32-C3.

# ESP32-C3-Universal-RapidFire-PS4-PS5-Controllers 

flash via web app here: https://vegueta-1.github.io/ESP32-C3-Universal-RapidFire-PS4-PS5-Controllers/web_flasher.html

Video Test on MW4 Beta: https://youtu.be/zJLvwunxujc

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
The ESP32‑C3 microcontroller sits between the controller board and the console, intercepting the R2 signal and providing advanced functionality:

- Rapid‑Fire (continuous or burst modes)

- Button Remapping (map tactile buttons to Square, Triangle, Circle, or X)

- Tactical Assists (Drop Shot, Jump Shot, Auto Reload)

- Macro Playback (up to 6‑step button sequences)

- Randomized Timing to reduce anti‑cheat pattern detection
  
- You configure everything through a web interface hosted on the ESP32's own WiFi access point.


Hardware & Connection

ESP32-C3 Super Mini ✅ Works (cheaper)


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

Seeed Studio Xiao ESP32-C3 ✅ Works

<img width="520" height="640" alt="Seeed-Studio-XIAO-ESP32-C3" src="https://github.com/user-attachments/assets/4aa57a51-3fe5-4fbe-8491-81e36bfdf7db" />

GPIO Mapping (Seeed Studio Xiao ESP32-C3)

D0- R2 Trigger (ADC + Output)

D1- Square button test point (Output)

D2- Triangle button test point (Output)

D4- Circle button test point (Output)

D5- X button test point (Output)

D3- Tactile switch A (to GND, Input with pull-up)

D10- Tactile switch B (to GND, Input with pull-up)

D9- (Optional) Status LED + resistor (inverted logic)


Need an Easy remap for both controller types.
<img width="1000" height="1000" alt="Easy Remap For Ps5 Controller" src="https://github.com/user-attachments/assets/777e0fc6-fcc5-49d4-ae6a-b43f877f113f" />
<img width="3060" height="4080" alt="Easy Remap For PS4 Controller" src="https://github.com/user-attachments/assets/59bc2e6d-f080-46a8-8ebd-cb565153e6bb" />

PS4 Wiring diagrams:
<img width="1600" height="1600" alt="ESP32-C3 Super Mini Original  Wiring Diagram JDM-040 And JDM-055" src="https://github.com/user-attachments/assets/eb79470f-f4b8-422a-876a-d89911c7d02c" />

<img width="1600" height="1600" alt="Seeed Studio Xiao ESP32-C3  Mini  Wiring Diagram JDM-040 And JDM-055" src="https://github.com/user-attachments/assets/ccaec47e-c002-4e07-b144-352b2210e6e3" />

<img width="4080" height="3060" alt="JDM-055 Install" src="https://github.com/user-attachments/assets/0e33c8ad-bbf4-483c-8883-722281a39788" />

<img width="4080" height="3060" alt="JDM-055 Install2" src="https://github.com/user-attachments/assets/ea5d5e5a-73b9-492a-9912-cbc2e35cb2b9" />

PS5 Wiring diagrams:
note for other boards starting from 30 to 50 versions you tap the R2 trigger from the easy remap flex. And use GPIO Mapping (Seeed Studio Xiao ESP32-C3) if you are installing the Seeed Studio Xiao ESP32-C3 Board for power and GND use Battery pads look Ps4 Diagram for more info.

<img width="1785" height="1176" alt="ESP32-C3 Super Mini Original  Wiring Diagram BDM-010 And BDM-020" src="https://github.com/user-attachments/assets/0a4be449-8e09-41e1-9fb8-fdb13dff9a1f" />



Connecting to the Web UI
Power on the ESP32 (it creates a WiFi AP)
Connect your phone/PC to WiFi: RapidFireMod_v0.9.11
Password: 12345678
Open browser → http://192.168.4.1
The themed dashboard loads


<img width="1192" height="1434" alt="Screenshot 2026-10-19 032810" src="https://github.com/user-attachments/assets/ae171142-6f4d-47c6-9662-fb7f037a19f1" />
<img width="1167" height="582" alt="ESP32-C3 Universal PS4 And PS5 Controller RapidFire Mod v0 9 9_UI" src="https://github.com/user-attachments/assets/e6aa8f23-7d78-4946-894a-b2c59cc16738" />

"For more details on how to use the mod and what each feature does, see the Rapid‑Fire Mod v0.9.11 — Complete User Guide PDF." attached on download link below.
[RapidFire Mod v0.9.11— Complete User Guide.pdf](https://github.com/user-attachments/files/33657652/RapidFire.Mod.v0.9.11.Complete.User.Guide.pdf)




