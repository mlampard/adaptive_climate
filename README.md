# Adaptive Climate
[![hacs_badge](https://img.shields.io/badge/HACS-Default-blue.svg?style=flat-square)](https://github.com/hacs/integration)
[![CI](https://github.com/msinhore/adaptive_climate/actions/workflows/ci.yml/badge.svg)](https://github.com/msinhore/adaptive_climate/actions/workflows/ci.yml)
[![Release](https://img.shields.io/github/v/release/msinhore/adaptive_climate?label=release&sort=semver&logo=github)](https://github.com/msinhore/adaptive_climate/releases)
[![Downloads](https://img.shields.io/github/downloads/msinhore/adaptive_climate/total)](https://github.com/msinhore/adaptive_climate/releases)
[![Stars](https://img.shields.io/github/stars/msinhore/adaptive_climate?style=flat-square)](https://github.com/msinhore/adaptive_climate/stargazers)
[![Licence](https://img.shields.io/github/license/msinhore/adaptive_climate.svg)](https://github.com/msinhore/adaptive_climate/blob/main/LICENSE)
[![Last commit](https://img.shields.io/github/last-commit/msinhore/adaptive_climate.svg)](https://github.com/msinhore/adaptive_climate)
![Project Status](https://img.shields.io/badge/status-active-brightgreen.svg)

[<img width="170" height="37" alt="Buy me a coffee" src="https://github.com/user-attachments/assets/0ce08a2b-1bc6-4f16-91f0-70c273cf4d47" />](https://buymeacoffee.com/msinhore)

A Home Assistant integration implementing ASHRAE 55 Adaptive Thermal Comfort for intelligent climate control.

---

## 🚀 Features

- 🔍 **ASHRAE 55 Adaptive Comfort**: Automatically adjusts comfort temperature using adaptive thermal comfort calculations, based on scientific standards.

- 🌡️ **Temperature and Humidity Monitoring**: Uses indoor/outdoor temperature sensors, and optionally humidity sensors, for precision climate control.

- 📊 **Running Mean Outdoor Temperature**: Tracks and computes historical outdoor temperatures to apply adaptive comfort adjustments.

- 🏖️ **Automatic Season Detection**: Dynamically detects seasons (summer, winter, spring, autumn) for contextual HVAC decisions.

- 🌀 **HVAC and Fan Control**: Automatically adjusts climate modes (cool, heat, fan_only, dry, off) and fan speeds based on real-time calculations.

- 📈 **Energy Save Mode**: Optimizes energy usage without compromising comfort. Must be explicitly enabled by the user.

- 🕹️ **Manual Override Detection**: Detects and respects manual user interventions, pausing automatic control when user takes manual control.

- 🛑 **User Power-off Handling**: If the user manually powers off the climate device, automatic control pauses until user powers it back on.

- 🔄 **Persistent State Memory**: Retains last states and control history across Home Assistant restarts.

- 📝 **Detailed Logging**: Records comfort calculations, HVAC decisions, and control logic for transparency and debugging.

- ⚙️ **Fully UI Configurable**: All configuration via Home Assistant options flow.

- 🌍 **Multi-language Support**: UI and entities available in multiple languages.

---

## 📊 Entities Provided

- **Binary Sensor**: ASHRAE Compliance
- **Select**: Comfort Category (I or II)
- **Switches**:
  - Energy Save Mode
  - Auto Mode

---

## 📦 Installation

### Via HACS (Recommended)

1. Install [HACS](https://hacs.xyz/)
2. Add this repository as a custom integration
3. Install "Adaptive Climate"
4. Restart Home Assistant
5. Add integration via Settings → Devices & Services → Add Integration → Adaptive Climate

---

## ⚙️ Configuration

- **Required**:
  - Climate Entity
  - Indoor Temperature Sensor
  - Outdoor Temperature Sensor

- **Optional**:
  - Indoor Humidity Sensor
  - Outdoor Humidity Sensor

All other options (comfort temperature range, aggressive cooling/heating thresholds, override adjustments, energy save mode, and auto mode) are configurable via the Home Assistant UI.

---

## 📈 How It Works

- Continuously monitors temperatures and humidity.
- Calculates adaptive comfort targets using ASHRAE 55.
- Controls HVAC and fan modes to optimize comfort.
- Tracks outdoor temperature history for accurate adaptive calculations.
- Detects and respects manual interventions.
- Energy saving behaviors are applied when explicitly enabled.

---

## ℹ️ Notes

- Supports **one climate entity** (multi-device support planned for v2.x).
- Prioritizes user control: never powers on devices after user shutdown.
- Does not perform fixed setpoint control: adapts dynamically to external and internal conditions.

---

## 🏛️ Standards & References

- **ASHRAE Standard 55-2020** - Thermal Environmental Conditions for Human Occupancy.
- **pythermalcomfort** library for scientific adaptive comfort calculations.

---

## 📄 License

MIT License – see [LICENSE](LICENSE).