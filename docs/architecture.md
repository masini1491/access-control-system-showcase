# 系統架構

## 高階角色

### Outdoor：室外端

- PN532 RFID／NFC 讀取器
- Android HCE 交易讀取器
- 指紋候選辨識軟體流程（Stage 2A；硬體驗證待完成）
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

## 既有配線再利用

呼叫線再利用屬於實體／安裝層，不屬於傳輸層。高階流程如下：

```text
實體按鈕 → Outdoor GPIO → ButtonEvent
        → 選定的傳輸方式 → Indoor Button Relay1–4
        → 繼電器接點 → 既有對講機呼叫迴路
```

RS485、LIN PHY 與 MQTT 屬於傳輸層；Indoor 端的繼電器重建屬於實體輸出層。呼叫 Relay 與開門 Relay 是不同功能，Indoor 的授權中心與既有存取控制邊界維持不變。
