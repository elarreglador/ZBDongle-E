# ZBDongle-E
Thread firmware setup in a ZBDongle-E

# BASH COMMANDS
Nuestro dispositivo es el 10c4:ea60 , verificamos que esta conectado a nuestro equipo
```
lsusb

Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 001 Device 002: ID 03f0:5341 HP, Inc HP Wireless Keyboard and Mouse
Bus 001 Device 004: ID 0bda:c821 Realtek Semiconductor Corp. Bluetooth Radio 
Bus 001 Device 005: ID 0573:1573 Zoran Co. Personal Media Division (Nogatech) USB Audio and HID
Bus 001 Device 036: ID 10c4:ea60 Silicon Labs CP210x UART Bridge
Bus 002 Device 001: ID 1d6b:0003 Linux Foundation 3.0 root hub
```
Descargamos e instalamos el nuevo firmware al USB dongle
```
universal-silabs-flasher --device /dev/ttyUSB0 \
    flash --firmware ./../Descargas/rcp-uart-802154-v4.3.1-zbdonglee-460800.gbl --allow-cross-flashing

2025-07-15 12:43:28.625 david-pc universal_silabs_flasher.flash INFO Extracted GBL metadata: NabuCasaMetadata(metadata_version=1, sdk_version='4.3.1', ezsp_version=None, ot_rcp_version=None, cpc_version=None, fw_type=<FirmwareImageType.MULTIPAN: 'multipan'>, fw_variant=None, baudrate=460800)
2025-07-15 12:43:28.626 david-pc universal_silabs_flasher.flasher INFO Probing ApplicationType.GECKO_BOOTLOADER at 115200 baud
2025-07-15 12:43:30.632 david-pc universal_silabs_flasher.flasher INFO Probing ApplicationType.CPC at 460800 baud
2025-07-15 12:43:34.941 david-pc universal_silabs_flasher.flasher INFO Probing ApplicationType.CPC at 115200 baud
2025-07-15 12:43:39.250 david-pc universal_silabs_flasher.flasher INFO Probing ApplicationType.CPC at 230400 baud
2025-07-15 12:43:43.561 david-pc universal_silabs_flasher.flasher INFO Probing ApplicationType.EZSP at 115200 baud
2025-07-15 12:43:48.571 david-pc universal_silabs_flasher.flasher INFO Probing ApplicationType.SPINEL at 460800 baud
2025-07-15 12:43:48.583 david-pc universal_silabs_flasher.flasher INFO Detected ApplicationType.SPINEL, version 'SL-OPENTHREAD/2.4.4.0_GitHub-7074a43e4' (2.4.4.0) at 460800 baudrate (bootloader baudrate None)
2025-07-15 12:43:48.583 david-pc universal_silabs_flasher.flash INFO Cross-flashing from FirmwareImageType.OPENTHREAD_RCP to FirmwareImageType.MULTIPAN
2025-07-15 12:43:48.589 david-pc universal_silabs_flasher.flasher INFO Probing ApplicationType.GECKO_BOOTLOADER at 115200 baud
2025-07-15 12:43:48.614 david-pc universal_silabs_flasher.flasher INFO Detected bootloader version '1.12.0'
2025-07-15 12:43:48.615 david-pc universal_silabs_flasher.flasher INFO Detected ApplicationType.GECKO_BOOTLOADER, version '1.12.0' at 115200 baudrate (bootloader baudrate 115200)
rcp-uart-802154-v4.3.1-zbdonglee-460800.gbl  [####################################]  100%   
```

# FUENTE
https://dialedin.com.au/blog/sonoff-zbdongle-e-rcp-firmware
