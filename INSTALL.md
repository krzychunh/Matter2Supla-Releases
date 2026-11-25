# Matter2Supla - Installation / Instalacja

## Requirements / Wymagania

- ESP32-C5 N16R8 or N32R8.
- USB connection and Python 3.
- Install esptool: `python -m pip install esptool`.
- Replace COM11 or COM13 with your actual serial port.

## N16R8 - FULL installation (0x0)

```powershell
python -m esptool --chip esp32c5 -p COM11 -b 460800 write-flash --flash-mode keep --flash-size keep --flash-freq keep 0x0 Matter2Supla-S7.18-RC4.7D.5-BETA-N16R8-FULL-0x0.bin
```

## N32R8 - FULL installation (0x0)

```powershell
python -m esptool --chip esp32c5 -p COM13 -b 115200 --no-stub write-flash --flash-mode keep --flash-size keep --flash-freq keep 0x0 Matter2Supla-S7.18-RC4.7D.5-BETA-N32R8-FULL-0x0.bin
```

WARNING: FULL installation overwrites NVS and removes existing configuration and Matter pairings.

UWAGA: instalacja FULL nadpisuje NVS oraz usuwa dotychczasowa konfiguracje i parowania Matter.

## N16R8 - APP update (0x20000)

```powershell
python -m esptool --chip esp32c5 -p COM11 -b 460800 write-flash 0x20000 Matter2Supla-S7.18-RC4.7D.5-BETA-N16R8-APP.bin
```

## N32R8 - APP update (0x20000)

```powershell
python -m esptool --chip esp32c5 -p COM13 -b 115200 --no-stub write-flash 0x20000 Matter2Supla-S7.18-RC4.7D.5-BETA-N32R8-APP.bin
```

APP updates require a compatible existing partition layout and normally preserve configuration.

## SHA256 verification

Windows: `Get-FileHash -Algorithm SHA256 filename.bin`

Linux: `sha256sum -c Matter2Supla-RC47D5-SHA256SUMS.txt`

## Beta warning

Back up your configuration before flashing. This firmware is experimental.
