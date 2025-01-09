
# Energy Meter Automation with PZEM004 and Blynk IoT

This project demonstrates the integration of the PZEM004T energy meter with an ESP8266 NodeMCU to monitor energy parameters such as voltage, current, power, energy, frequency, and power factor. The data is visualized in real-time on the Blynk IoT platform and an I2C LCD.

## Components Used

- **ESP8266 NodeMCU (12E Lolin)**: Microcontroller for controlling the system.
- **PZEM004T V3 Energy Meter**: Energy meter for measuring voltage, current, power, energy, frequency, and power factor.
- **I2C LCD 20x4**: For local display of energy data.
- **Blynk IoT App**: For real-time visualization of data.
- **Jumper Wires and Power Supply**: For connecting components.

## Circuit Diagram

- **PZEM004T**:
  - TX -> RX (ESP8266)
  - RX -> TX (ESP8266)
  - VCC -> 3.3V (ESP8266)
  - GND -> GND (ESP8266)
- **I2C LCD**:
  - SDA -> D2
  - SCL -> D1
  - VCC -> 3.3V or Vin
  - GND -> GND

## Software Requirements

- **Arduino IDE**: For programming the ESP8266.
- **Blynk App**: To create and control the IoT dashboard.
- **Libraries**:
  - [BlynkSimpleEsp8266](https://github.com/blynkkk/blynk-library/blob/master/src/BlynkSimpleEsp8266.h)
  - [PZEM004Tv30](https://github.com/mandulaj/PZEM-004T-v30)
  - [LiquidCrystal_I2C](https://github.com/johnrickman/LiquidCrystal_I2C)

## Installation Steps

1. **Install Arduino IDE**:
   - Download and install Arduino IDE from [here](https://www.arduino.cc/en/software).
   - Add ESP8266 board support by following this guide: [ESP8266 Installation Guide](https://github.com/esp8266/Arduino).

2. **Install Libraries**:
   - Go to Arduino IDE > Sketch > Include Library > Manage Libraries.
   - Install the following libraries:
     - **Blynk**
     - **PZEM004Tv30**
     - **LiquidCrystal_I2C**

3. **Set up the Blynk App**:
   - Create a new project in the Blynk app.
   - Select **ESP8266** as the device.
   - Get the **auth token** from the app and replace it in the code.

4. **Upload the Code**:
   - Connect the ESP8266 to your computer via USB.
   - Open the provided Arduino code in the IDE.
   - Select the correct board (NodeMCU 1.0) and port.
   - Upload the code to the ESP8266.

5. **Connect the Hardware**:
   - Connect the PZEM004T energy meter and the I2C LCD as per the circuit diagram.
   - Ensure proper power connections.

## Features

- **Voltage Monitoring ⚡**: Displays the current voltage.
- **Current Monitoring 💡**: Shows the current in amps.
- **Power Monitoring 🔋**: Displays the power consumption in watts.
- **Energy Consumption 🔌**: Measures the energy in kilowatt-hours (kWh).
- **Frequency Monitoring 📶**: Displays the frequency of the system.
- **Power Factor ⚙️**: Shows the power factor (PF).

## Output

- **Local Display**:
  - LCD shows voltage, current, power, energy, frequency, and power factor.
  
- **Cloud Display**:
  - Data is sent to the Blynk App, where you can visualize it on custom widgets in real-time.

## Code Overview

1. **Setup**:
   - Initializes the LCD and Blynk connection.
   - Sets up the PZEM004T energy meter to read data.
   - Displays introductory messages on the LCD.

2. **Loop**:
   - Continuously reads data from the PZEM004T energy meter.
   - Sends data to the Blynk app every 5 seconds.
   - Displays real-time data on the LCD.

## Troubleshooting

- **No Data on Blynk App**:
  - Make sure the ESP8266 is connected to the internet and the Blynk server is reachable.
  - Check your Wi-Fi credentials (SSID and Password).

- **LCD Display Issues**:
  - Ensure the I2C LCD is properly connected and recognized by the ESP8266.
  - Try adjusting the I2C address if necessary.

