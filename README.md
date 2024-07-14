# Home-assistant-ESP32
Home assistand board using ESP32 controlled with MQTT protocol.

## Main purpose of Home assistant board
The project was created with the thought of controlling LED strips with MQTT protocol via phone app. A moment later, the idea of controlling and connecting many devices appeared such as water pump for watering plants plants, temperature sensors, lamps and so on.
![Alt text](MainBoard/MainBoard.jpg?raw=true "Main board prototype version 0.2.")

Prototype mainboard version 0.1 consist of:
- Espressif ESP32 S2 mini 1 chip,
- CP2102N series USB to UART bridge controller,
- XT30PW-M connector for powering board with up to 15V DC external power source,
- Onboard 3.3V and 5V buck converters capable of 3A current load each,
- 4 I/O molex KK254 4 pin connectors,
- 8 output molex KK254 2 pin connectors,
- 2 connectors for additional expansion of the mainboard,
- UART pin header for externel programmer connection.

### I/O connectors
Each connector consists of ground and voltage pins (jumper selection 3.3V or 5V), output signal and input signal with ESD protection schottky diodes.

### Output connectors
Output connector consists of voltage pin (jumper selection 3.3V, 5V or external power from XT30PW-M connector) and n-mosfet switching to ground. Those headers are capable of PWM control. Used DMN3023L mosfets are capable of 30V and up to 6.3A continous drain current. There is also super fast recovery DFLU1200-7 diode protecting device from reverse current flow.

### Additional expansion connectors
Those connectors uses the rest of gpio ESP pins and also provide SPI and I2C protocols.

## ACControl board
This board allows to control AC powered devices.
Control signals are seperated from AC side with SFH6156-1T optotransistors for safety purpose. AZ921-1A-12DE relays are used for switching AC current.
![Alt text](ACControl/ACControl.jpg?raw=true "ACControl prototype version 0.1.")

## TempSensRTC
Addidtional board for temperature measurement. Can be used with MAX31865 chip for resisatance temperature detectors (RTDs) or with MAX31855 chip that allows to use theremocouples like K-type thermocouple. 
![Alt text](TempSensRTC/TempSensRTC.jpg?raw=true "TempSensRTC prototype version 0.1.")
