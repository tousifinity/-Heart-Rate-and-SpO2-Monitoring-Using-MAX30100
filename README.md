# Heart Rate and SpO2 Monitoring Using MAX30100

This project utilizes the **MAX30100 Pulse Oximeter** sensor to measure heart rate (bpm) and blood oxygen saturation (SpO2) levels in real-time. The code interfaces the sensor with an Arduino through I2C communication and displays the data on the serial monitor. It also detects individual heartbeats and logs them.

## Features
- **Real-Time Heart Rate Monitoring**: Measures heartbeats per minute (bpm).
- **Blood Oxygen Saturation (SpO2)**: Monitors the percentage of oxygenated hemoglobin in the blood.
- **Beat Detection**: Outputs "Beat!" on the serial monitor for each detected heartbeat.
- **Compact and Efficient**: Periodically reports readings every second for smooth monitoring.

## Hardware Requirements
- **MAX30100 Pulse Oximeter Sensor**
- **Arduino Board** (e.g., Arduino Uno, Nano, or similar)
- **Jumper Wires**
- **Power Source**

## Libraries Used
- [`MAX30100_PulseOximeter`](https://github.com/oxullo/Arduino-MAX30100)


## Wiring Configuration
| MAX30100 Pin | Arduino Pin  |
|--------------|--------------|
| VCC          | 3.3V/5V      |
| GND          | GND          |
| SDA          | A4 (I2C Data)|
| SCL          | A5 (I2C Clock)|


## Setup Instructions
1. **Install Libraries**:
   - Download and install the `MAX30100_PulseOximeter` library from the Arduino Library Manager.
   - Ensure the `Wire` library is included (pre-installed with Arduino IDE).

2. **Hardware Connections**:
   - Connect the MAX30100 sensor to the Arduino as per the wiring configuration table.

3. **Upload Code**:
   - Open the Arduino IDE, copy the provided code, and upload it to the Arduino board.

4. **Serial Monitor**:
   - Open the serial monitor with a baud rate of `115200` to view the heart rate and SpO2 data.

## How It Works
1. **Initialization**:
   - The `pox.begin()` function initializes the MAX30100 sensor.
   - The IR LED current is set to `MAX30100_LED_CURR_7_6MA` for accurate readings.

2. **Heartbeat Detection**:
   - A callback function (`onBeatDetected`) logs each detected heartbeat.

3. **Reporting Data**:
   - Every second, the heart rate and SpO2 values are printed on the serial monitor.
