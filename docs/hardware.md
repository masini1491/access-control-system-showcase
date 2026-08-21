# 硬體

## 目前與規劃中的硬體

| 元件 | 狀態 |
|---|---|
| ESP32-C3 SuperMini | ✅ 目前已驗證的建置／硬體基準 |
| ESP32-C6 SuperMini | 📋 規劃中；需獨立確認 board、pinout 與硬體驗證 |
| PN532 | ✅ RFID／NFC 讀取器整合 |
| MAX3485／RS485 | ✅ 已驗證的本機傳輸基準 |
| TJA1021 類 transceiver | 🧪 替代 PHY；尚待硬體驗證 |
| R503S | 🧪 未來主要指紋目標；尚未進行硬體驗證 |
| R503／AS608 | 📋 相容方向，需各型號獨立確認 |
| Relay modules | ✅ 門鎖解鎖輸出路徑，由 Indoor 控制 |

文件只提供一般硬體方向，不公開住家線路、IP、Wi-Fi、實際 hostname、裝置識別值或可直接利用的 physical bypass 資訊。

## 指紋模組方向

未來指紋模組預計使用保留的 AUX UART 能力。R503／R503S 的文件基準僅假設 OFF／RED／BLUE 雙色 LED 能力，不假設 full RGB、混色或動畫；目前不包含 driver、enrollment 或硬體結果。
