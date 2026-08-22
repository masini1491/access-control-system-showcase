# 發展路線

以下為高階方向，不承諾日期：

- 🧪 Door Protocol MQTT 剩餘 broker／SESSION／ACL hardware-network 驗證
- 🧪 R503S 指紋模組硬體驗證
- 📋 Fingerprint enrollment／delete、LED 與 Indoor credential integration
- 🧪 TTL ↔ LIN／TJA1021 硬體驗證
- 📋 polarity-tolerant／protected PT6 front-end 與實際電氣校正
- 📋 Home Assistant 整合
- 📋 Matter 選配整合

Production firmware、protocol contract 與安全實作仍以 private development repository 為唯一事實來源；本 showcase 不作為開發 repository。

### GPIO Expansion

MCP23017 I²C GPIO expander 曾被評估為降低多 Button／Relay configuration 對 ESP32 native GPIO 消耗的可能 future option；目前 **Evaluated / Deferred / Not Implemented**，不是 supported hardware 或 current architecture。
