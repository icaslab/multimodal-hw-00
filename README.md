
▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄
>⚔️⚔️⚔️ **THIS REPO IS NOT FINISHED. IT IS ONGOING WORK. DO NOT CHANGE! ** ⚔️⚔️⚔️
▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄▀▄

## Multimodal Transcutaneous Monitor Hardware (PtcO₂ / PtcCO₂ / SpO₂ / EDA)
   .--------------------.
   |  Multimodal PCB 🧠 |
   |  PtcO₂ • PtcCO₂    |
   |  SpO₂  •  EDA      |
   |                    |
   |  [ ] [ ] [ ] [ ]   |
   '----o----------o----'
        |  USB-C  |
        '--------'
### Info
Hardware design files (Altium Designer) for a wearable research prototype that combines **transcutaneous gas sensing (PtcO₂ / PtcCO₂)**, **pulse oximetry (SpO₂)**, and **electrodermal activity (EDA)** in one platform.

### Key Specs
- **MCU:** STM32WB55RG (dual-core Cortex-M4/M0+, BLE)
- **Analog Front End:** ADPD7000 (optical + bio-impedance/EDA sensing)
- **Storage:** 512 Mb QuadSPI Flash 
- **Power Input:** USB-C (2.0) or 3.7V Li-Po with battery charging

### Sensors / Peripherals
- **BME280** (Temp/Humidity/Pressure) over I²C (`0x76`)
- **ADXL367** (Accelerometer) over I²C (`0x1D ?`)
- **AM1805** (RTC + hardware watchdog) over I²C (`0x69`)

### Power Management
- **BQ21088** charger with power-path + ship mode
- **LTC3100** rails:
  - **1.8V** (low-noise AFE)
  - **3.3V** (MCU + digital)
  - **5.0V** (optical / LED drive domain)

### Repository Organization
- `Datasheets/`  
  - Find component datasheets here.

### Schematic Sheets 
- `01-multimodal-powersupply-connections.SchDoc`
- `02-multimodal-pmic.SchDoc`
- `03-multimodal-battery-charger.SchDoc`
- `04-multimodal-flash.SchDoc`
- `05-multimodal-analogfrontend.SchDoc`
- `06-multimodal-microcontroller.SchDoc`
- `07-multimodal-microcontroller-oscillators.SchDoc`
- `08-multimodal-microcontroller-switches-display.SchDoc`
- `09-multimodal-microcontroller-rf.SchDoc`
- `10-multimodal-combined-sensor.SchDoc`
- `11-multimodal-accelerometer.SchDoc`
- `12-multimodal-RTC.SchDoc`


⠀⠀⢸⡿⢦⣄⠀⢀⣠⣴⣶⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠘⣷⠀⠉⠛⠛⠉⢰⡇⠀⠀⠘⣷⣦⣾⡇⠀⠀⠀⠀⠀⠀⠀
⠀⢀⣰⠿⠀⠀⠀⠀⠀⢿⡁⠀⢀⣴⣿⣿⣿⣶⡄⠀⠀⠀⠀⠀⠀
⣴⣿⣁⡀⠀⠀⠀⠀⠀⠀⠻⣦⡀⠀⠀⢿⠃⠀⢀⣤⡀⠀⠀⠀⠀
⠀⠈⠉⠛⣿⡀⠀⣰⠟⠛⠛⠛⠛⠀⠀⠀⠀⣠⡾⢻⡇⠀⠀⠀⠀
⠀⠀⠀⠀⠈⣷⣼⠏⠀⠀⠀⢻⣟⠻⠿⢶⡾⠋⠀⢸⡇⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠘⠃⠀⣴⠀⠀⠈⢻⣆⠀⠀⠀⠀⠀⠀⠻⢶⣤⣀⠀
⠀⠀⠀⠀⠀⠘⢷⣾⣿⣤⣄⠀⢈⣿⠀⠀⠀⠀⠀⠀⠀⢀⣉⣿⠿
⠀⠀⠀⠀⠀⢀⣾⠿⣿⡏⠉⢠⣾⠃⠀⠀⠀⠀⠀⢀⣾⠛⠋⠁⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠙⠃⠀⣿⡷⠿⠟⠛⢿⣦⡀⢸⡇⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀  ⠀⠙⢿⣿⠃⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀  ⠀⠉⠀⠀⠀⠀⠀
