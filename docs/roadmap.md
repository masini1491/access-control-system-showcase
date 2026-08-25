# 發展路線

以下為高階方向，不承諾日期：

- 🧪 Door Protocol MQTT 剩餘 broker／SESSION／ACL 硬體／網路驗證
- 🧪 R503S 指紋模組硬體驗證
- 📋 Fingerprint enrollment／delete、LED 與 Indoor credential integration
- 🧪 TTL ↔ LIN／TJA1021 硬體驗證
- 📋 可容忍極性／具保護的 PT6 前端與實際電氣校正
- 📋 Home Assistant 整合
- 📋 Matter 選配整合

正式韌體、protocol contract 與安全實作仍以 private development repository 為唯一事實來源；本 showcase 不作為開發 repository。

### GPIO 擴充

MCP23017 I²C GPIO expander 曾被評估為降低多 Button／Relay configuration 對 ESP32 native GPIO 消耗的可能未來選項；目前為 **已評估／延後／尚未實作**，不是目前支援的硬體，也不是現行架構的一部分。
