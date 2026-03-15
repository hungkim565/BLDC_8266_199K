## Build nhanh ra fw.bin (ESP8266)

### Cách 1: Arduino CLI (khuyến nghị)

1) Cài `arduino-cli` và đảm bảo chạy được lệnh `arduino-cli` trong PowerShell.

- Windows (winget):

```powershell
winget install ArduinoSA.CLI
```

Tài liệu: https://arduino.github.io/arduino-cli/latest/installation/

Nếu bạn chưa muốn cài hệ thống, script build có thể tự tải `arduino-cli.exe` về thư mục `.arduino/arduino-cli/`.
Lúc đó bạn không gõ được `arduino-cli version` trực tiếp, nhưng có thể chạy:

```powershell
.\.arduino\arduino-cli\arduino-cli.exe version
```

2) Chạy build (mặc định board NodeMCU 1.0: `esp8266:esp8266:nodemcuv2`):

```powershell
powershell -ExecutionPolicy Bypass -File .\tools\build.ps1
```

Kết quả sẽ ghi ra:
- `forOTA/fw.bin`

### Tuỳ chọn

- Cài core ESP8266 và một số thư viện cơ bản:

```powershell
powershell -ExecutionPolicy Bypass -File .\tools\build.ps1 -InstallCore -InstallLibs
```

- Đổi board (FQBN):

```powershell
powershell -ExecutionPolicy Bypass -File .\tools\build.ps1 -Fqbn esp8266:esp8266:generic
```

- Tự build lại khi file thay đổi:

```powershell
powershell -ExecutionPolicy Bypass -File .\tools\build.ps1 -Watch
```
