# CAR WITH IR WHICH FOLLOW THE OBJECT

## Project Overview
This Arduino project creates a car that follows objects using an IR sensor. When the IR sensor detects an object, the car moves forward; otherwise, it stops.

## Components Required
- Arduino Uno
- Adafruit Motor Shield v1 (L293D based)
- 4x DC Motors
- IR Sensor (analog output)
- Jumper wires
- Chassis for mounting components
- Battery pack (for motors)

## Pin Configuration
| Component         | Arduino Pin/Port   | Description                  |
|------------------|--------------------|------------------------------|
| Motor 1 (Back Left)  | Motor Shield M1   | Controlled via AFMotor library |
| Motor 2 (Back Right) | Motor Shield M2   | Controlled via AFMotor library |
| Motor 3 (Front Left) | Motor Shield M3   | Controlled via AFMotor library |
| Motor 4 (Front Right)| Motor Shield M4   | Controlled via AFMotor library |
| IR Sensor         | A0                 | Analog input                 |

- Connect the IR sensor's analog output to Arduino's A0 pin.
- Mount the motor shield on the Arduino Uno and connect the motors to M1, M2, M3, and M4 outputs.

## Circuit Diagram
```
[IR Sensor] ----> [A0 Arduino Uno]
[Motor 1] ------> [M1 Motor Shield]
[Motor 2] ------> [M2 Motor Shield]
[Motor 3] ------> [M3 Motor Shield]
[Motor 4] ------> [M4 Motor Shield]
```

## Software Setup
1. Install the [Adafruit Motor Shield v1 library](https://github.com/adafruit/Adafruit-Motor-Shield-library) in the Arduino IDE.
2. Open the provided `CAR WITH IR WHICH FOLLOW THE OBJECT.cpp` file in Arduino IDE.
3. Upload the code to your Arduino Uno.

## How It Works
- The IR sensor reads analog values from pin A0.
- If the sensor detects an object (value below threshold), all motors move forward.
- If no object is detected, all motors stop.
- You can adjust the detection threshold in the code (`int threshold = 500;`).

## Usage Instructions
1. Assemble the car chassis and mount the motors.
2. Attach the motor shield to the Arduino Uno.
3. Connect the motors to the motor shield (M1-M4).
4. Connect the IR sensor's analog output to A0 on Arduino.
5. Power the Arduino and motor shield appropriately.
6. Upload the code and test the car. Adjust the threshold if needed for your IR sensor.

## Troubleshooting
- If the car does not move, check motor connections and power supply.
- If the car moves without detecting an object, adjust the threshold value.
- Ensure the IR sensor is properly connected and functional.

## License
This project is open-source and free to use for educational purposes.
