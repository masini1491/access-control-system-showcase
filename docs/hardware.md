# Hardware

## 目前與規劃中的硬體

| 元件 | 狀態 |
|---|---|
| ESP32-C3 SuperMini | ✅ current validated build／hardware baseline |
| ESP32-C6 SuperMini | 📋 planned；需獨立 board、pinout 與 hardware validation |
| PN532 | ✅ RFID／NFC reader integration |
| MAX3485／RS485 | ✅ validated local transport baseline |
| TJA1021 類 transceiver | 🧪 alternative PHY；hardware validation pending |
| R503S | 🧪 primary future fingerprint target；hardware validation not performed |
| R503／AS608 | 📋 compatibility direction，需各型號獨立確認 |
| Relay modules | ✅ door unlock output path，由 Indoor 控制 |

文件只提供一般硬體方向，不公開住家線路、IP、Wi-Fi、實際 hostname、裝置識別值或可直接利用的 physical bypass 資訊。

## Fingerprint direction

未來 fingerprint 預計使用保留的 AUX UART capability。R503／R503S 的文件基準僅假設 OFF／RED／BLUE 雙色 LED capability，不假設 full RGB、混色或動畫；目前不包含 driver、enrollment 或 hardware result。
