⚔️ Work in Progress: This repository is under active development. Please do not make changes. ⚔️

### Multimodal Transcutaneous Monitor Hardware (PtcO₂ / PtcCO₂ / SpO₂ / BIA)

### Key Specs
- **MCU:** STM32WB55RGV6 (dual-core Cortex-M4/M0+, BLE 5.0) — VFQFPN68
- **Analog Front End:** ADPD7000 (optical + bio-impedance/BIA sensing) — 36-ball WLCSP, 0.4mm pitch
- **Storage:** S25FL512S — 512 Mb QuadSPI Flash (5×5 BGA)
- **Power Input:** USB-C (2.0) or 3.7V Li-Po with integrated battery charging

### Sensors / Peripherals
- **BME280** (Temp/Humidity/Pressure) over I²C (`0x76`)
- **ADXL367** (Accelerometer) over I²C (`0x53`)

### Power Management
- **MAX20345** single-chip PMIC (WLP-56, 0.4mm pitch) with:
  - Integrated Li-Po charger (ISET = 10kΩ → ~200mA charge current)
  - NTC thermistor monitoring (SEMITEC 103AT-11)
  - **Buck 2:** 1.8V analog rail (`1V8A`) — low-noise AFE supply
  - **Buck 3:** 3.3V digital rail (`3V3D`) — MCU + digital peripherals
  - **Buck-Boost:** 5.0V LED drive domain (`5V_LED`) — optical front end
  - **LDO 1:** 1.8V digital rail (`1V8D`)
  - **LDO 2:** 3.3V LED rail (`3V3_LED`)
  - **LDO 3:** Alternative output (`L3OUT`)
  - **Load Switches:** LSW1, LSW2 not used either 
  - Buck 1 unused — disabled via I²C

### PCB
- **Stackup:** 6-layer HDI (Sig+Pwr / GND / Sig / PwR / GND / Sig)
- **HDI:** Stacked/staggered µVias (100µm laser drill, 250µm pad, via-in-pad with epoxy fill + cap plating)

### Repository Organization
- `Datasheets/`  
  - Find component datasheets here.

### Schematic Sheets
- `00-multimodal-coversheet.SchDoc`
- `01-multimodal-powersupply.SchDoc`
- `04-multimodal-flash.SchDoc`
- `05-multimodal-analogfrontend.SchDoc`
- `06-multimodal-analogfrontend-PPG.SchDoc`
- `07-multimodal-microcontroller.SchDoc`
- `08-multimodal-microcontroller-oscillators.SchDoc`
- `10-multimodal-microcontroller-rf.SchDoc`
- `11-multimodal-combined-sensor.SchDoc`
- `12-multimodal-accelerometer.SchDoc`
- `13-multimodal-connections.SchDoc`

```text
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
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠙⢿⣿⠃⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠉⠀⠀⠀
```
