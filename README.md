## Build nhanh ra fw.bin (ESP8266)

### Cách 1: Arduino CLI (khuyến nghị)

1) Cài `arduino-cli` và đảm bảo chạy được lệnh `arduino-cli` trong PowerShell.

2) Chạy build (mặc định board: `esp8266:esp8266:nodemcuv2`):

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
