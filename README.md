
# ESP32 with DHT22 module and publish to MQTT



## Installation
- Please prepare the folder for the project, for me it is D:\ESP32
- Clone my git repository

- Run my project with Docker in Powershell on Windows

```bash
  cd D:\ESP32
  docker run --rm -it -v "${PWD}:/data" -w "/data" espressif/idf bash
```

```bash
  idf.py create-project esp32dht22 
  cd esp32dht22
  idf.py set-target esp32
```
Then drag and drop all files in my repository to folder esp32dht22

Make sure to config Wifi SSID and password in menuconfig in Powershell
```bash
  idf.py menuconfig
```
- Build
```bash
  idf.py Build
```

## Flash
- Go download [Flash Download Tools](https://www.espressif.com/en/support/download/other-tools) from Espressif
- Extract then go inside the folder and open flash_download_tool_3.9.5.exe (my version is 3.9.5)
- Setting the property then click OK
```bash
ChipType:ESP32
WorkMode:Develop
LoadMode:UART
```
- Setting build files
```
D:\ESP32\esp32dht22\build\bootloader\bootloader.bin             | @0x1000
D:\ESP32\esp32dht22\build\esp32dht22.bin                        | 0x10000
D:\ESP32\esp32dht22\build\partition_table\partition-table.bin   | 0x8000
```
Check COM and BAUD with your port connected to esp32 and click START
## Result
- open PuTTY
```bash
Serial line: COM9
Speed:11520
Connection type: Serial
```
don't forget to change the Serial line to be your PORT connected to esp32
