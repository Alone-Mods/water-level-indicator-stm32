#  – Non-Contact Water Level Indicator

An STM32-based water level monitoring system using ultrasonic distance measurement to detect water levels without direct contact with water.

## Project Overview

Mokxi is an embedded systems project developed using the STM32F411CEU6 microcontroller and HC-SR04 ultrasonic sensor.

The system measures the distance between the sensor and the water surface and indicates the water level using three LEDs.

## Hardware Components

- STM32F411CEU6 Black Pill
- HC-SR04 Ultrasonic Sensor
- Green LED
- Yellow LED
- Red LED
- Active Buzzer
- Resistors
- Breadboard and jumper wires
- ST-LINK programmer

## Pin Configuration

| Component | STM32 Pin |
|---|---|
| HC-SR04 TRIG | PA0 |
| HC-SR04 ECHO | PA1 |
| Green LED | PA5 |
| Yellow LED | PA6 |
| Red LED | PA7 |
| Buzzer control | PB15 |

**Note:** HC-SR04 ECHO uses a voltage divider to reduce the signal voltage before connecting to PA1. The buzzer requires a suitable transistor driver.

## Water Level Indication

The system uses the measured distance between the ultrasonic sensor and the water surface.

| Distance | Water Level | Indicator |
|---|---|---|
| Above 35 cm | Low | Red LED |
| 15–35 cm | Medium | Yellow LED |
| 1–15 cm | High | Green LED |
| 1 cm or less | Full | All three LEDs |

The thresholds can be adjusted according to the dimensions of the container.

## Working Principle

1. The STM32 sends a trigger pulse to the HC-SR04 sensor.
2. The ultrasonic sensor transmits an ultrasonic wave.
3. The reflected wave produces an ECHO pulse.
4. The STM32 measures the ECHO pulse duration using TIM2.
5. The distance is calculated from the measured pulse duration.
6. LEDs indicate the corresponding water level.

## Software and Tools

- STM32CubeIDE
- STM32 HAL Library
- Embedded C
- STM32CubeMX configuration
- Git and GitHub

## Project Structure

```text
Water_Level_Indicator/
├── Core/
│   ├── Inc/
│   ├── Src/
│   └── Startup/
├── Drivers/
│   ├── CMSIS/
│   └── STM32F4xx_HAL_Driver/
├── .ioc
├── .gitignore
├── .project
├── .cproject
└── README.md
```

## Project Status

- [x] STM32F411CEU6 configuration
- [x] HC-SR04 integration
- [x] LED indicators
- [x] Ultrasonic distance measurement firmware
- [x] GitHub repository setup
- [ ] Final hardware validation
- [ ] Buzzer driver integration
- [ ] Project documentation and demonstration

## Author

**Aswin Pramod**

GitHub: [@Alone-Mods](https://github.com/Alone-Mods)

---

*Built as an embedded systems engineering project using STM32 technology.*
