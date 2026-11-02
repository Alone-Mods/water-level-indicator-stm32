# 💧 ECHO32 — Non-Contact Water Level Indicator

<div align="center">

  <img src="https://img.shields.io/badge/ECHO32-Engineered%20to%20Sense-7C3AED?style=for-the-badge&logo=stmicroelectronics&logoColor=white" alt="ECHO32"/>

  **An STM32-based ultrasonic water-level monitoring system.**

  [![Platform](https://img.shields.io/badge/Platform-STM32F411CEU6-blue?style=flat-square&logo=stmicroelectronics)](https://www.st.com/)
  [![Language](https://img.shields.io/badge/Language-Embedded%20C-00599C?style=flat-square&logo=c)](https://en.wikipedia.org/wiki/C_(programming_language))
  [![IDE](https://img.shields.io/badge/IDE-STM32CubeIDE-03234B?style=flat-square)](https://www.st.com/en/development-tools/stm32cubeide.html)
 
  <br/>

  <img src="https://github.com/Alone-Mods.png" width="110" alt="Developer Avatar"/>

  **Developed by [Alone-Mods](https://github.com/Alone-Mods)**

</div>

---

## 📌 About the Project

**ECHO32** is a non-contact water-level monitoring system developed using the **STM32F411CEU6 Black Pill** microcontroller and an **HC-SR04 ultrasonic sensor**.

The system measures the distance between the sensor and the water surface using ultrasonic waves. Based on the measured distance, it indicates the water level through three LEDs:

- 🔴 Red LED — Low water level
- 🟡 Yellow LED — Medium water level
- 🟢 Green LED — High water level

A buzzer provides an additional warning when the water level reaches the configured low-level condition.

Unlike conventional contact-based indicators, ECHO32 measures the water level without placing electrical probes inside the water.

## 🎯 Project Objectives

- Develop a non-contact water-level monitoring system.
- Measure water-surface distance using ultrasonic technology.
- Process sensor readings using an STM32 microcontroller.
- Display different water levels through LED indicators.
- Provide an audible warning for low-water conditions.
- Demonstrate embedded programming using STM32CubeIDE and HAL libraries.

## 🏆 Project Approval

<div align="center">

  ![Teacher Approved](https://img.shields.io/badge/PROJECT-TEACHER%20APPROVED-16A34A?style=for-the-badge&logo=checkmarx&logoColor=white)

  **ECHO32 has been reviewed, validated and approved by our project teacher.**

</div>

---

## ⚙️ How It Works

ECHO32 operates using the principle of ultrasonic distance measurement.

1. The STM32 sends a trigger pulse to the HC-SR04 sensor.
2. The sensor transmits ultrasonic waves towards the water surface.
3. The waves reflect from the water surface and return to the sensor.
4. The sensor generates an ECHO pulse based on the time taken by the waves to return.
5. The STM32 measures the ECHO pulse duration.
6. The distance is calculated and compared with predefined thresholds.
7. The corresponding LED and buzzer indicators are activated.

### 📐 Distance Calculation

The distance is calculated using:

\[
\text{Distance} = \frac{\text{Time} \times \text{Speed of Sound}}{2}
\]

The approximate speed of sound used is 0.0343 cm/µs.

The division by 2 accounts for the ultrasonic wave's journey to the water surface and back.

---

## 🔩 Hardware Components

| Component | Quantity | Purpose |
|---|---:|---|
| STM32F411CEU6 Black Pill | 1 | Main microcontroller |
| HC-SR04 Ultrasonic Sensor | 1 | Distance measurement |
| Green LED | 1 | High water indication |
| Yellow LED | 1 | Medium water indication |
| Red LED | 1 | Low water indication |
| 220Ω Resistors | 3 | LED current limiting |
| Voltage divider / level shifter | 1 | ECHO voltage protection |
| Active Buzzer | 1 | Audible warning |
| Transistor driver | 1 | Buzzer switching |
| Breadboard | 1 | Circuit assembly |
| Jumper Wires | As required | Connections |
| ST-LINK Programmer | 1 | Firmware programming and debugging |

## 🔌 Pin Configuration

| Component | STM32 GPIO Pin |
|---|---|
| HC-SR04 TRIG | PA0 |
| HC-SR04 ECHO | PA1 |
| Green LED | PA5 |
| Yellow LED | PA6 |
| Red LED | PA7 |
| Buzzer Driver | PB15 |

### ⚠️ Important Electrical Considerations

- The HC-SR04 requires a suitable 5V power supply.
- Its ECHO output can reach 5V, while STM32 GPIO operates at 3.3V logic.
- Use an appropriately designed voltage divider or logic-level shifter before connecting ECHO to PA1.
- Connect the grounds of the STM32, sensor and external supply together.
- Use a suitable transistor or MOSFET driver for the buzzer rather than driving it directly from a GPIO pin.
- Check the component ratings and STM32 pin specifications before powering the circuit.

---

## 💡 Water-Level Indication

The firmware uses the distance between the sensor and the water surface to determine the water level.

| Measured Distance | Water Condition | Indicator |
|---|---|---|
| Above 35 cm | Low water | 🔴 Red LED + Buzzer |
| 15–35 cm | Medium water | 🟡 Yellow LED |
| 1–15 cm | High water | 🟢 Green LED |
| At or below 1 cm | Full-level indication | All LEDs + Buzzer |

**Note:** These are demonstration thresholds and should be adjusted according to the dimensions of the container. The HC-SR04 also has a practical minimum measurement distance, so validate the full-level threshold with the actual sensor setup.

---

## 🧠 Software and Technologies

| Technology | Usage |
|---|---|
| Embedded C | Firmware development |
| STM32CubeIDE | Development environment |
| STM32 HAL | Hardware abstraction and peripheral control |
| GPIO | LED, trigger and buzzer control |
| TIM2 | Microsecond timing |
| HC-SR04 | Ultrasonic distance sensing |
| ST-LINK | Programming and debugging |

---

# 🚀 Getting Started

<div align="center">

  ![Start Here](https://img.shields.io/badge/START%20HERE-ECHO32-7C3AED?style=for-the-badge&logo=github&logoColor=white)
  ![Beginner Friendly](https://img.shields.io/badge/LEVEL-Beginner-22C55E?style=for-the-badge)
  ![Teacher Approved](https://img.shields.io/badge/PROJECT-APPROVED-16A34A?style=for-the-badge)

  **Ready to build your own ECHO32? Let's get started!**

</div>

### 🧰 Step 1 — Requirements

Before starting, make sure you have:

**Hardware**
- STM32F411CEU6 Black Pill
- HC-SR04 ultrasonic sensor
- LEDs and resistors
- Suitable ECHO voltage-level shifting circuit
- Buzzer and transistor driver
- Breadboard and jumper wires
- ST-LINK programmer
- Regulated 5V supply for the sensor

**Software**
- [STM32CubeIDE](https://www.st.com/en/development-tools/stm32cubeide.html)
- [Git](https://git-scm.com/downloads) (optional)

### 📥 Step 2 — Download the Project

Choose either method.

**Option A — Download ZIP**

1. Open the [ECHO32 GitHub Repository](https://github.com/Alone-Mods/water-level-indicator-stm32).
2. Click the green **Code** button.
3. Select **Download ZIP**.
4. Extract the downloaded ZIP file.

**Option B — Clone using Git**

Open your terminal and execute:

```bash
git clone https://github.com/Alone-Mods/water-level-indicator-stm32.git
```

### 💻 Step 3 — Import into STM32CubeIDE

1. Open STM32CubeIDE.
2. Select **File → Import**.
3. Choose **General → Existing Projects into Workspace**.
4. Browse to the extracted project directory.
5. Select the project.
6. Click **Finish**.

### 🔌 Step 4 — Connect the Hardware

Connect the components according to the pin configuration table above.

Make sure:
- The sensor faces downward towards the water surface.
- The HC-SR04 receives a suitable 5V supply.
- ECHO is connected through a suitable level-shifting circuit.
- All grounds are connected together.
- LEDs have individual current-limiting resistors.
- The buzzer uses a suitable driver circuit.

### ⚙️ Step 5 — Build the Firmware

1. Open the project in STM32CubeIDE.
2. Allow the IDE to finish indexing.
3. Click the **Build** button (hammer icon).
4. Check the Console for build errors.

![Build](https://img.shields.io/badge/BUILD-Compile%20Project-2563EB?style=for-the-badge)

### ⚡ Step 6 — Flash the STM32

1. Connect ST-LINK to the Black Pill using SWDIO, SWCLK and GND.
2. Ensure the board has an appropriate power supply.
3. Select **Run → Debug** or **Run → Run** in STM32CubeIDE.
4. Wait for the firmware to be programmed.
5. Restart the board if necessary.

### 🧪 Step 7 — Test the System

1. Place the ultrasonic sensor above the container.
2. Power on the system.
3. Gradually add water to the container.
4. Observe the LED indicators as the water level changes.
5. Check the buzzer response when the configured low-water threshold is reached.

### 🎚️ Step 8 — Customize the Thresholds

You can modify the distance thresholds in `main.c` to suit your container.

Example:

```c
if (distance > 35.0f)
{
    // Low water level
}
else if (distance > 15.0f)
{
    // Medium water level
}
else if (distance > 1.0f)
{
    // High water level
}
else
{
    // Full-level indication
}
```

Adjust the values according to your container dimensions and sensor's practical measurement range.

---

## 🛠️ Troubleshooting

| Problem | Possible Solution |
|---|---|
| LEDs are not glowing | Check LED polarity, resistors and GPIO connections |
| Sensor is not responding | Check its 5V supply, GND and wiring |
| Incorrect distance readings | Check ECHO level shifting and sensor alignment |
| STM32 is not detected | Check ST-LINK SWDIO, SWCLK and GND |
| Buzzer is not working | Check transistor driver, polarity and supply |
| Build errors | Check project configuration and STM32CubeIDE setup |

---

## 📂 Project Structure

```text
Water_Level_Indicator/
│
├── Core/
│   ├── Inc/
│   │   └── main.h
│   │
│   └── Src/
│       ├── main.c
│       ├── stm32f4xx_it.c
│       └── stm32f4xx_hal_msp.c
│
├── Drivers/
│   ├── CMSIS/
│   └── STM32F4xx_HAL_Driver/
│
├── Debug/
│
├── Water_Level_Indicator.ioc
├── .project
├── .cproject
├── .gitignore
└── README.md
```

*The exact generated files and folders may vary depending on the STM32CubeIDE build configuration.*

---

## 🔮 Future Improvements

Some possible improvements for future versions:

- Add an OLED or LCD display for numerical water-level readings.
- Introduce Wi-Fi or Bluetooth connectivity for remote monitoring.
- Develop a mobile application for live water-level updates.
- Add automatic water-pump control.
- Implement data logging and historical water-level monitoring.
- Improve measurement stability with filtering and calibration.

---

## 🤝 Contributing

Contributions and suggestions are welcome!

If you would like to improve ECHO32:

1. Fork this repository.
2. Create a new branch.
3. Make your changes.
4. Submit a pull request.

Every improvement counts! 💜

---

## 👨‍💻 Developer

<div align="center">

  <img src="https://github.com/Alone-Mods.png" width="120" alt="Aswin's GitHub Avatar"/>

  ### Aswin — Alone-Mods

  B.Tech Cyber Security Student

  [![GitHub](https://img.shields.io/badge/GitHub-Alone--Mods-181717?style=for-the-badge&logo=github)](https://github.com/Alone-Mods)

  *Building, learning and exploring the world of technology.*

</div>

---

<div align="center">

  ## 💜 ECHO32

  **ENGINEERED TO SENSE.**

  *Designed with electronics. Developed with code. Driven by curiosity.*

  ⭐ If you find this project interesting, consider giving the repository a star!

</div>
