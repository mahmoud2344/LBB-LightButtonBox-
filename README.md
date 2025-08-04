# LBB-LightButtonBox-
LightButtonBox is a customizable button box interface designed for sim racing, and other control setups. It supports both keyboard and joystick (vJoy) modes, allowing you to map physical buttons and pedals directly to your PC.
---

## Features

-  Ultra-low latency input (via serial over USB)
- Two input modes:
  - **Keyboard Mode**: Emulate real key presses
  - **Joystick Mode (vJoy)**: Emulate joystick buttons and analog axes (e.g., throttle, brake, clutch)
- Clean GUI:
  - Serial port connection
  - Input mode selector (keyboard or joystick)
  - Developer terminal for debugging
- Pedal support using ADC for analog input (throttle, brake, clutch)
- Auto-saving of button and mode settings

---

## Getting Started

1. **Download the `.exe` file from the [Releases](https://github.com/mahmoud2344/LBB-LightButtonBox-/releases)**  
   *(No need to install Python or other dependencies)*

2. **Run the app**  
   *(Allow driver permissions if needed)*

3. **Connect your microcontroller (e.g., ESP32)**  
   - Select your preferred input mode (recommended: Joystick)
   - Press **Connect** — you're ready to map and use buttons

---

## Serial Communication Format

The app can work with **any microcontroller**, not just ESP32, as long as it sends the following format over the serial port:

- **Button press/release:**
	
*(BTN1_PRESSED)*
*(BTN1_RELEASED)*


- **Analog input (e.g., pedals):**

	*(THROTTLE:12345 (converted value fo vjoy compatibility))*
*(BRAKE:8000)*
*(CLUTCH:32767)*


These messages should be sent **terminated with `\r\n`** for best compatibility.

---

## Requirements

- Windows (x64)
- [vJoy Driver](https://github.com/BrunnerInnovation/vJoy/releases) installed *(only required for joystick mode)*
- A microcontroller that can send serial data over USB

---

## Coming Soon

- **WiFi support** for wireless setups
- A complete **LBB Starter Pack**:
- `.bin` firmware for **ESP32-C3**
- Flash tool for fast setup
- LazyOS-based minimal runtime for button/pedal detection
- Configurable GPIO roles: Digital input, ADC, or output
- Game-specific profiles

---

## Developer Tools

- Password-protected **Dev Mode**
- Serial log viewer
- Live CLI terminal for low-level communication
- Debug latency metrics with high-precision timestamps

---

Made with Love by [Mahmoud Fakhry]
## Licensing

This app is **free for personal use only**. Do not sell, distribute, or modify it without permission.

This project relies on several open-source libraries. While the app itself is closed-source, we acknowledge and respect the open-source work it builds upon.

A complete list of used libraries and licenses can be found in the LICENSE.txt file.
