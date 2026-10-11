# Smart Energy Meter with Electricity Theft Detection Using FreeRTOS

## Overview

The Smart Energy Meter with Theft Detection is an ESP32-based embedded system designed to monitor electrical parameters and identify potential electricity theft conditions by comparing phase and neutral current measurements.

The system uses FreeRTOS multitasking to separate measurement, calculation, theft detection, display, and IoT communication functions. An LCD displays the readings locally, while the Blynk IoT platform provides remote monitoring and status visualization.

The project demonstrates the practical application of Real-Time Operating Systems (RTOS), embedded programming, electrical parameter monitoring, and IoT-based supervision.

## Objectives

- Monitor electrical parameters using an ESP32-based system.
- Compare phase and neutral current measurements to identify possible abnormalities.
- Implement independent tasks using FreeRTOS.
- Display electrical readings and detection status on an LCD.
- Send monitoring information to a Blynk IoT dashboard.
- Demonstrate task-based embedded system design.

## Technologies Used

- **Microcontroller:** ESP32
- **Operating System:** FreeRTOS
- **Programming Language:** C/C++
- **IoT Platform:** Blynk IoT
- **Display:** 20×4 I2C LCD
- **Firmware Environment:** Arduino IDE with ESP32 support
- **Key Concepts:** Multitasking, task scheduling, sensor monitoring, threshold-based detection, IoT communication

## Hardware Components

- ESP32 development board
- Current sensing arrangement for phase and neutral measurements
- LCD with I2C interface
- Voltage sensing or simulation input, as implemented
- Supporting wiring and power supply

Add the exact sensor models and other components used in your implementation.

## System Working

1. **Measurement:** The system reads the phase and neutral current inputs.
2. **Parameter Calculation:** Electrical measurements are processed to obtain the required readings.
3. **Theft Detection:** The measured currents are compared using the implemented threshold and mismatch logic.
4. **Display:** Current readings and the detection status are shown on the LCD.
5. **IoT Communication:** The system sends selected readings and status information to Blynk for remote visualization.

A detected current mismatch indicates a possible abnormal condition. It does not independently prove electricity theft, because sensor errors, wiring issues, and other conditions can also cause mismatches.

## FreeRTOS Task Architecture

The firmware separates the main functions into independent tasks:

- **Sensing Task:** Reads the current measurements.
- **Calculation Task:** Processes measurements and calculates the required electrical parameters.
- **Theft Detection Task:** Evaluates current mismatch and detection thresholds.
- **Display Task:** Updates the LCD with readings and status.
- **Communication Task:** Sends the monitoring data to Blynk IoT.

Task priorities, timing, synchronization, and shared-data handling should be documented according to the actual firmware implementation.

## IoT Monitoring

The Blynk dashboard displays selected system parameters through virtual pins:

- **V10:** Theft Status
- **V11:** Current
- **V12:** Power
- **V13:** Abnormal Count
- **V14:** Threshold

These virtual pin assignments describe the dashboard configuration used in this project.

## Project Gallery

### Hardware Setup
<img width="1042" height="824" alt="Copy of rtos ppt (2)" src="https://github.com/user-attachments/assets/5afebf97-346a-40fa-8b96-a66cf2b046c5" />
<img width="1121" height="841" alt="Copy of rtos ppt (3)" src="https://github.com/user-attachments/assets/e889f825-06e2-47ee-9ed3-04d0c30ce257" />


### LCD Output
<img width="1121" height="841" alt="Copy of rtos ppt (3)" src="https://github.com/user-attachments/assets/fdbbd711-b1c0-48f7-bf66-d4521085d709" />

### Blynk IoT Dashboard
<img width="688" height="918" alt="Copy of rtos ppt (4)" src="https://github.com/user-attachments/assets/8653adc3-6378-4397-8597-d5ed61a38933" />

### Theft Detection Test
<img width="1330" height="647" alt="Screenshot 2026-10-12 011158" src="https://github.com/user-attachments/assets/1a139c33-1c0e-4f6f-be3d-1357fded2ec1" /><img width="672" height="616" alt="Screenshot 2026-10-12 011022" src="https://github.com/user-attachments/assets/9327866a-ec73-4980-921f-db9456dc2a09" />
<img width="658" height="606" alt="Screenshot 2026-10-12 011043" src="https://github.com/user-attachments/assets/531bf7e8-64db-4501-91f2-173d1a714bfc" />


## Testing and Results

The project was tested using the implemented current measurement and mismatch detection logic.

Document the actual test cases, including:

- Normal operation with phase and neutral measurements within the expected tolerance.
- A simulated abnormal condition with a current mismatch.
- LCD status updates.
- Blynk dashboard updates and communication behavior.

Include measured values, expected outputs, and observed outputs from your tests. Do not claim accuracy or performance figures without supporting measurements.

## Applications

- Educational smart energy metering prototypes
- Embedded systems and RTOS demonstrations
- Remote monitoring of electrical parameters
- Experimental detection of abnormal current conditions
- IoT-enabled energy monitoring systems

## Future Scope

- Improve detection reliability through sensor calibration and filtering.
- Add energy consumption logging and historical analysis.
- Introduce event timestamps and alerts.
- Evaluate fault conditions separately from suspected theft.
- Explore improved power measurement and communication reliability.

## Conclusion

This project combines ESP32-based energy monitoring, FreeRTOS multitasking, mismatch-based abnormality detection, LCD display, and Blynk IoT visualization. It provides practical experience in designing task-oriented embedded applications with local and remote monitoring capabilities.

## Repository Structure

```text
Smart-Energy-Meter-Theft-Detection-RTOS/
├── README.md
├── src/
│   └── main.ino
├── images/
│   ├── hardware-setup.jpg
│   ├── lcd-output.jpg
│   ├── blynk-dashboard.png
│   └── theft-detection-test.png
├── docs/
│   ├── block-diagram.png
│   └── task-flowchart.png
└── results/
    └── test-results.md
```

Adapt the structure to the files you actually have.

## Getting Started

1. Clone or download the repository.
2. Open the source code in Arduino IDE with ESP32 board support installed.
3. Install the libraries required by the firmware, including the LCD, current measurement, and Blynk libraries as applicable.
4. Configure the actual pin assignments and sensing arrangement.
5. Configure Blynk credentials securely without publishing authentication tokens.
6. Upload the firmware and observe the LCD and dashboard outputs.

Follow the source code and circuit documentation for the exact setup.

---

**Project Domain:** Embedded Systems | FreeRTOS | IoT | Energy Monitoring

**Author:** [Meghana Jadhav]
