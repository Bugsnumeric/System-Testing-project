Diagrama proiectului:

<p align="center">
  <img src="diagram.png" width="600">
</p>


Componente folosite impreuna cu detalii despre acestea:

| Component | Part Number | Package | Function | Datasheet |
|-----------|------------|---------|----------|-----------|
| MCU | nRF52840-QIAA-R | aQFN73 (7x7) | Microcontroller + BLE + USB | [Datasheet](https://docs.nordicsemi.com/) |
| Charger / Power Path | BQ25180YBGR | DSBGA-8 | Li-Ion/LiPo charger with power path | [Datasheet](https://www.ti.com/lit/ds/symlink/bq25180.pdf) |
| Buck-Boost Regulator | RT6160AWSC | WLCSP-15 | 3.3V system rail regulator | [Datasheet](https://www.richtek.com/assets/product_file/RT6160A/DS6160A-05.pdf) |
| Fuel Gauge | MAX17048G+T10 | DFN-8 (2x2) | Battery SOC monitoring | [Datasheet](https://www.analog.com/media/en/technical-documentation/data-sheets/MAX17048-MAX17049.pdf) |
| Accelerometer | BMA421 | LGA-12 (2x2) | Step counting + motion wake | [Datasheet](https://jlcpcb.com/partdetail/Bosch_Sensortec-BMA421/C5242966) |
| Haptic Driver | DRV2605LDGSR | VSSOP-10 | ERM motor driver with effects library | [Datasheet](https://www.ti.com/lit/ds/symlink/drv2605l.pdf) |
| PFET (EPD power) | SI2301CDS | SOT-23 | E-paper display power gating | [Datasheet](https://jlcpcb.com/partdetail/Changjiang_Electronics_Tech_CJ-SI2301CDS/C10487) |
| USB ESD Protection | USBLC6-2SC6Y | SOT-23-6 | ESD protection on USB data lines | [Datasheet](https://www.st.com/resource/en/datasheet/usblc6-2.pdf) |
| USB Type-C Connector | KH-TYPE-C-16P | 16-pin SMD | USB charging + data | [Datasheet](#) |


Descriere funcționalitate hardware

Interfețe:

I2C: încărcător LiPo, regulator DC/DC, IMU, fuel gauge, driver haptic
SPI: display e-paper

Sheet 1:

Încărcătorul LiPo gestionează încărcarea bateriei
Regulatorul DC/DC asigură o tensiune stabilă de 3.3V pentru sistem
IMU (accelerometru) măsoară accelerația pe 3 axe și permite funcții precum numărarea pașilor
Microcontrollerul nRF52840 coordonează toate funcțiile plăcii
Interfața SWD este utilizată pentru programare și debug

Sheet 2:

Circuitul de comandă pentru e-paper alimentează și controlează display-ul
Conectorul e-paper realizează legătura fizică cu display-ul
Fuel gauge monitorizează nivelul de încărcare al bateriei
Conectorul USB-C permite alimentarea și transferul de date
Protecția ESD previne deteriorarea cauzată de descărcări electrostatice
Driverul haptic controlează motorul de vibrație
Butoanele oferă interfața de control pentru utilizator


## Descriere pini nRF52840  

| Pin | Descriere |
|-----|----------|
| VDD | Alimentare 3V3 |
| DCC | Power regulation |
| DEC4 | Power regulation |
| VSS | GND |
| P0.31 / AIN7-4 | Nefolosit |
| P0.02 / AIN0 | SPI SCK (clock pentru display) |
| P0.02 / AIN0 | SPI MOSI (master output slave in) |
| P1.15–P1.12 | Nefolosit |
| DEC2 | GND, power regulation |
| P1.12–P1.11 | Nefolosit |
| VDD | Alimentare 3V3 |
| XC2, XC1 | Oscilator X1 (32 MHz) |
| DEC3 | GND |
| DEC6 | Power regulation |
| VSS_PA | Alimentare antenă |
| ANT | Conectare antenă |
| P0.10 / NFC2 | Semnal alertă baterie (Fuel Gauge) |
| P0.09 / NFC1 | Nefolosit |
| DEC5 | GND, power regulation |
| P1.07–P1.03 | Nefolosit |
| P1.02 | Buton Down |
| P1.01 | Control alimentare display |
| SWDIO, SWDCLK | Programare și debug |
| VDD | Alimentare 3V3 |
| VSS_PAD | GND |
| P1.00 | SWO (debug) |
| P0.25–P0.19 | Nefolosit |
| P0.18 / RESET | Pin Reset |
| P0.17, P0.16, P0.15 | Interfață display |
| P0.13, P0.14 | Butoane Enter / Up |
| D-, D+ | USB (transmisie diferențială) |
| VBUS | Alimentare USB 5V |
| DEC3V3 | GND (intern, power regulation) |
| DCCH | Nefolosit |
| VDDH, VDD | Alimentare 3V3 |
| P0.12 | Enable driver haptic |
| P0.11 | Alertă alimentare (de la LiPo Charger) |
| P1.09 | Nefolosit |
| P1.08, P0.08 | Interrupții IMU |
| P0.07, P0.06 | I2C (SCL, SDA) |
| P0.05 / AIN3 | Chip Select display |
| P0.04 / AIN2, P0.27, P0.26 | Nefolosit |
| XL2, XL1 | Oscilator X2 (32 kHz) |
| DEC1 | GND, power regulation |

