# 系統架構

## 高階角色

### Outdoor：室外端

- PN532 RFID／NFC 讀取器
- Android HCE 交易讀取器
- 未來指紋憑證候選取得
- 按鈕與選配感測器事件來源

### Indoor：室內端

- 唯一憑證授權中心
- 白名單與完整憑證比對
- Relay 控制、存取決策與事件整合

## 事件流程

```text
憑證／按鈕
        ↓
      Outdoor
        ↓ 已驗證的本機或網路傳輸
      Indoor
        ↓ 白名單授權
     允許／拒絕
        ↓
      Relay
```

Outdoor 是憑證候選來源，不在本地執行白名單授權，也不直接決定開門。公開文件不包含 production key、Pair ID、真實白名單值或可直接利用的安全實作細節。
