# Architecture

## 高階角色

### Outdoor

- PN532 RFID／NFC reader
- Android HCE transaction reader
- 未來 fingerprint candidate acquisition
- Button 與選配感測器事件來源

### Indoor

- 唯一 credential authorization authority
- whitelist 與 exact credential matching
- relay control、access decision 與 event integration

## 事件流程

```text
Credential / Button
        ↓
      Outdoor
        ↓ authenticated local or network transport
      Indoor
        ↓ whitelist authorization
   ALLOW / DENY
        ↓
      Relay
```

Outdoor 是 credential candidate producer，不在本地執行 whitelist authorization，也不直接決定開門。公開文件不包含 production key、Pair ID、真實 whitelist 值或可直接利用的安全實作細節。
