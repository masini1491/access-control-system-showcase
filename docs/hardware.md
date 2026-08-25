# 硬體

## 目前與規劃中的硬體

| 元件 | 狀態 |
|---|---|
| ESP32-C3 SuperMini | ✅ 目前已驗證的建置／硬體基準 |
| ESP32-C6 SuperMini | 📋 規劃中；需獨立確認板卡、pinout 與硬體驗證 |
| PN532 | ✅ RFID／NFC 讀取器整合 |
| MAX3485／RS485 | ✅ 已驗證的本機傳輸基準 |
| TJA1021 類收發器 | 🧪 替代 PHY；尚待硬體驗證 |
| GPS/GNSS | ❌ 已退役；GPIO20/21 改保留為 Fingerprint AUX UART 方向 |
| R503S | 🧪 主要硬體目標；軟體 scan/match diagnostics 已完成，硬體驗證待完成 |
| R503／AS608 | 📋 相容方向，需各型號獨立確認；不宣稱與 R503S 完全等價 |
| Relay 模組 | ✅ 門鎖解鎖輸出路徑，由 Indoor 控制 |

文件只提供一般硬體方向，不公開住家線路、IP、Wi-Fi、實際 hostname、裝置識別值或可直接利用的實體繞過資訊。

## 傳統四線式對講機相容性

本專案的主要適用情境是既有傳統四線式對講機改造（retrofit）。銘陽牌與俞氏牌是主要實裝／驗證對象；明谷／機智品牌系統屬於潛在相容、尚待個別型號實測；其他四線式系統則需逐案評估。

「四線式」只是系統類型的高階描述，不代表不同品牌或型號具有相同的電氣介面。實裝前應確認供電、GND 參考、呼叫、語音、開門、門狀態／PT 或其他輔助訊號，以及實際電壓與極性。公開展示不提供實際住家配線、地址或敏感量測細節，也不宣稱官方認證或通用相容。

文中品牌與商標僅用於說明測試與相容性對象；本專案與相關原廠無隸屬、授權或合作關係。

## 呼叫線再利用的電氣邊界

高階改造架構可將原實體呼叫按鈕接到 Outdoor GPIO 輸入，並由 Indoor Relay 接點重建原本的呼叫接點。Relay 接點閉合時，原對講機呼叫迴路的電壓／電流會經過接點；ESP32 GPIO 僅處於控制側，不直接承載該呼叫迴路。實際接點額定值、隔離能力、呼叫電源、共用端、個別呼叫輸入與極性，必須依品牌／型號及現場量測確認。

這不代表所有 Relay 模組都有相同的隔離／接點額定值，也不代表所有四線式系統可直接套用。

## PT Door State 限制

PT Door State 軟體流程與台架模擬已完成；實際對講機 PT 可能相對對講機 GND 呈負極性，且不同安裝環境的量值可能不同。舊的僅支援正電壓電阻分壓原型已失效並標記為 **DO NOT INSTALL**；可容忍極性／具保護的 PT6 前端與完整電氣校正仍待完成。

這不代表所有傳統四線式對講機具有相同 polarity 或 voltage range，也不公開住家量測細節。

## 指紋模組方向

Fingerprint Stage 2A 已完成軟體側 UART detection、scan／feature extraction 與 sensor-local search diagnostics，並建立受界定的 worker ownership；GPIO20／GPIO21 保留為 Fingerprint AUX UART 方向。主要硬體目標為 R503S，R503／AS608 仍須逐型號驗證。

目前尚未接入正式開門授權；Indoor 仍是唯一授權中心。enrollment／delete、LED control 與硬體驗證仍待完成。R503／R503S baseline LED 僅描述 OFF／RED／BLUE 方向，不假設 full RGB、混色或動畫。
