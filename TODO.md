## Translation
- Translate the tutorial (handbook) from Japanese to English, Spanish, and Catalan.

## Research and exploration
- Investigate ways to improve the current proposed sensory, electronics, and software components. Ideas:
  - Use something like the Myo armband to capture EMG activity around arm muscles: https://wearables.com/products/myo
  - Consider an open hardware/software alternative to the Myo armband: https://psylink.me/

- In the meanwhile could be interesting to get a try in a pure mechanical open prothesic arm. Take a look at https://www.makerhand.com/

## PCB improvements
- OTA upgradability.
- Bluetooth support, at least for the initial training phase.
- FreeRTOS-capable; we want minimal user delay.
- Explore edge inference capabilities.

## Software improvements
- Android/iOS app for initial training and adjustment of the sensory band and device.
- Real C programming with FreeRTOS.

## Prototype manufacturing
- PCBs and electronics assembly: https://jlcpcb.com/
- 3D printing with durable materials: https://jlc3dp.com/

## Mapping atmega328p to nodeMCU

Function,ATmega Pin,NodeMCU Pin,NodeMCU GPIO,Notes / Constraints
I2C SDA,A4,D2,GPIO 4,Mandatory for ADC/Display
I2C SCL,A5,D1,GPIO 5,Mandatory for ADC/Display
Serial RX,D0,RX,GPIO 3,Used for USB programming
Serial TX,D1,TX,GPIO 1,Used for USB programming
Servo 1,D9,D5,GPIO 14,Safe PWM pin
Servo 2,D6,D6,GPIO 12,Safe PWM pin
Servo 3,D5,D7,GPIO 13,Safe PWM pin
Button 1,A6,D3*,GPIO 0,Warning: Must be HIGH at boot
Button 2,A7,D4*,GPIO 2,Warning: Must be HIGH at boot
Button 3,A0,D0*,GPIO 16,Warning: No internal Pullup resistor
Button 4,D10,D8*,GPIO 15,Warning: Must be LOW at boot
Sensor (Sens),A1,ADS1115 A0,External,Connect to ADS1115 Module
Joystick X (AX),A2,ADS1115 A1,External,Connect to ADS1115 Module
Joystick Y (AY),A3,ADS1115 A2,External,Connect to ADS1115 Module