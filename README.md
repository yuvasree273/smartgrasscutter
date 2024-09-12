# Smart Grass Cutting Robot

This project demonstrates the design and implementation of a smart grass-cutting robot controlled remotely using the **Blynk** mobile application. The robot uses a Wi-Fi-enabled **NodeMCU ESP8266** module to communicate with the Blynk cloud platform, allowing users to control the robot's movements and speed from a smartphone.

## Features

- **Remote Control:** Use the Blynk app to start, stop, and control the robot's movement in different directions (forward, backward, left, right).
- **Speed Adjustment:** Adjust the robot's speed using a slider in the app.
- **Wireless Operation:** The robot is controlled over Wi-Fi, eliminating the need for physical controllers.

## Hardware Requirements

- NodeMCU ESP8266
- L298N Motor Driver
- BO Motors and Wheels
- Cutter Blade
- 3.7V Lithium-Ion Battery
- Chassis
- Switch
- Jumper Wires

## Software Requirements

- [Arduino IDE](https://www.arduino.cc/en/software)
- [Blynk App](https://blynk.io/en/getting-started)

## Circuit Diagram

The following connections are made between the NodeMCU ESP8266 and the motor driver:

| NodeMCU Pin | Motor Driver Pin | Description                |
|-------------|------------------|----------------------------|
| D6 (PWM)    | ENA              | Enable motor A             |
| D5 (PWM)    | ENB              | Enable motor B             |
| D1          | IN1              | Motor A direction control  |
| D2          | IN2              | Motor A direction control  |
| D3          | IN3              | Motor B direction control  |
| D4          | IN4              | Motor B direction control  |

## Blynk App Setup

1. **Create a new project** in the Blynk app.
2. Choose **NodeMCU** as the device.
3. Add the following widgets:
   - **Button (V0)**: Forward movement control.
   - **Button (V1)**: Backward movement control.
   - **Button (V2)**: Left movement control.
   - **Button (V3)**: Right movement control.
   - **Slider (V5)**: Speed control (0 to 1).

4. **Auth Token**: After creating the project, copy the auth token provided by Blynk and use it in your code.

## How It Works

- **Blynk App Controls:** The robot’s movement (forward, backward, left, right) and speed are controlled using virtual pins in the Blynk app.
- **Motor Control:** The L298N motor driver allows for precise control over the speed and direction of the motors using PWM signals from the NodeMCU.
- **Direction Logic:** The `controlRobot()` function in the code reads the values from the app and triggers the respective motor movements.

## How to Run

1. Download and install the **Blynk** app on your smartphone.
2. Set up the project as mentioned above.
3. Connect your NodeMCU to your local Wi-Fi network by providing the SSID and password in the code.
4. Upload the code to the NodeMCU using the Arduino IDE.
5. Control the robot using the Blynk app.

## Future Improvements

- Integration of **sensors** to enable autonomous movement.
- Addition of **obstacle avoidance** using ultrasonic sensors.
- Enhancement of **battery life** and power management.
  
---
