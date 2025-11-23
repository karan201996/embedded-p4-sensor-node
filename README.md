# embedded-p4-sensor-node  

## Overview  
This project implements a sensor node using an I2C sensor and a PC dashboard. It demonstrates how to interface with sensors via I2C, apply simple data filtering, and stream the data to a host computer for visualization using a Python script.  

## Hardware Requirements  
- Microcontroller board with I2C interface (e.g., Raspberry Pi Pico, STM32).  
- I2C sensor (e.g., BME280 for temperature/humidity/pressure).  
- USB cable for power and serial communication.  

## Software Requirements  
- Pico SDK or STM32 HAL drivers.  
- Python 3 with `pyserial` and `matplotlib` (for PC dashboard).  
- CMake build system and Ninja.  

## Build & Flash Instructions  
1. Clone this repository and initialize the SDK (set `PICO_SDK_PATH` or HAL).  
2. Configure the I2C pins and sensor address in `src/main.c`.  
3. Build the project using CMake: `mkdir build && cd build && cmake .. && make -j`.  
4. Flash the binary to your board using the appropriate tool (e.g., `picotool load -f firmware.uf2`).  
5. On the host PC, run `python3 tools/dashboard.py` to start the serial dashboard.  

## Features  
- Periodic sampling of I2C sensor data.  
- Simple low-pass filtering to smooth sensor readings.  
- Serial protocol sending formatted data over USB/UART.  
- Python dashboard plotting real-time sensor data.  

## Demo  
Connect the board to your computer, open the Python dashboard, and observe live graphs of the sensor data as it updates. Adjust sensor settings in the firmware and watch the changes reflected in real time.  

## Future Work  
- Add support for multiple sensors and additional communication protocols.  
- Implement configurable sampling rates via serial commands.  
- Integrate data logging and timestamping to SD card or flash.
