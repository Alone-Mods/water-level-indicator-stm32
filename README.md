 <div align="center">

<img src="https://github.com/Alone-Mods.png" width="130" height="130" alt="Aswin's GitHub avatar"/>

# ⚡ E C H O 3 2

### NON-CONTACT WATER LEVEL MONITOR

**Ultrasonic sensing. Intelligent monitoring. STM32 powered.**

<img src="https://img.shields.io/badge/STM32-F411CEU6-6C63FF?style=for-the-badge&logo=stmicroelectronics&logoColor=white"/>
<img src="https://img.shields.io/badge/Embedded_C-00D1FF?style=for-the-badge&logo=c&logoColor=white"/>
<img src="https://img.shields.io/badge/STM32CubeIDE-8A2BE2?style=for-the-badge"/>

*Engineered to Sense.*

[Explore Repository](https://github.com/Alone-Mods/water-level-indicator-stm32) · [Report Issues](https://github.com/Alone-Mods/water-level-indicator-stm32/issues)

</div>

---

## 🌌 About ECHO32

**ECHO32** is a non-contact water-level monitoring system developed using the STM32F411CEU6 Black Pill microcontroller and HC-SR04 ultrasonic sensor.

It measures the distance between the sensor and the water surface without requiring direct contact with water.

The STM32 processes the measured distance and activates visual indicators according to the detected water level.

> Small hardware. Smart sensing. Practical engineering.

## ⚙️ Hardware Components

| Component | Purpose |
|:---|:---|
| STM32F411CEU6 Black Pill | Main controller |
| HC-SR04 | Ultrasonic distance measurement |
| Green LED | High water level |
| Yellow LED | Medium water level |
| Red LED | Low water level |
| Active buzzer | Audio alert |
| ST-LINK | Programming and debugging |

## 🔌 Pin Configuration

| Component | STM32 GPIO |
|:---|:---:|
| HC-SR04 TRIG | `PA0` |
| HC-SR04 ECHO | `PA1` |
| Green LED | `PA5` |
| Yellow LED | `PA6` |
| Red LED | `PA7` |
| Buzzer driver | `PB15` |

**Electrical note:** HC-SR04 ECHO uses a voltage divider before connecting to PA1. The buzzer requires a suitable transistor driver.

## 💡 Water Level Detection

Configured for a demonstration container approximately 50 cm high.

| Distance from sensor | Water condition | Indicator |
|:---:|:---|:---:|
| Above 35 cm | Low | 🔴 RED |
| 15–35 cm | Medium | 🟡 YELLOW |
| 1–15 cm | High | 🟢 GREEN |
| 1 cm or less | Full | 🚨 ALL LEDs |

*Thresholds can be calibrated for different container dimensions.*

## 🧠 Working Principle

```text
       ┌─────────────────────┐
       │       HC-SR04       │
       │  Ultrasonic Sensor  │
       └──────────┬──────────┘
                  │
             TRIG / ECHO
                  │
       ┌──────────▼──────────┐
       │   STM32F411CEU6     │
       │                     │
       │  Distance Measure   │
       │  TIM2 / HAL         │
       └──────────┬──────────┘
                  │
          Water Level Logic
                  │
       ┌──────────▼──────────┐
       │   LED INDICATORS    │
       │                     │
       │   🔴   🟡   🟢      │
       └─────────────────────┘
                  │
              Audio Alert
```

### Measurement Process

1. STM32 generates a trigger pulse.
2. HC-SR04 emits an ultrasonic wave.
3. The wave reflects from the water surface.
4. The sensor generates an ECHO pulse.
5. STM32 TIM2 measures the ECHO pulse duration.
6. Distance is calculated using the speed of sound.
7. The appropriate water-level indicator is activated.

## 🛠️ Technology Stack

<div align="center">

<img src="https://skillicons.dev/icons?i=c,git,github,vscode" alt="Technology stack"/>

<br/><br/>

<img src="https://img.shields.io/badge/STM32-HAL_Library-6C63FF?style=flat-square"/>
<img src="https://img.shields.io/badge/STM32CubeMX-Configuration-00D1FF?style=flat-square"/>
<img src="https://img.shields.io/badge/Git-Version_Control-F05032?style=flat-square"/>

</div>

## 📁 Project Structure

```text
ECHO32/
├── Core/
│   ├── Inc/
│   ├── Src/
│   └── Startup/
├── Drivers/
│   ├── CMSIS/
│   └── STM32F4xx_HAL_Driver/
├── .settings/
├── .gitignore
├── .ioc
├── .project
├── .cproject
└── README.md
```

## 🚧 Development Progress

- [x] STM32F411CEU6 configuration
- [x] HC-SR04 sensor integration
- [x] LED indicator circuit
- [x] Ultrasonic distance measurement firmware
- [x] Water-level threshold logic
- [x] GitHub repository setup
- [ ] Final hardware validation
- [ ] Buzzer driver integration
- [ ] Final project demonstration

## 👨‍💻 Developer

<div align="center">

<img src="https://github.com/Alone-Mods.png" width="110" alt="Developer avatar"/>

### ALONE MODS

**Engineering  | Cyber Security | S5 PROJECT **

[![GitHub](https://img.shields.io/badge/GitHub-Alone--Mods-181717?style=for-the-badge&logo=github)](https://github.com/Alone-Mods)

</div>

---

<div align="center">

### ⚡ ECHO32 — ENGINEERED TO SENSE.

*Designed and developed by AsHH.*

**© 2026 ECHO32**

</div>
