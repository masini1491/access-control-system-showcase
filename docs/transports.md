# 傳輸方式

## RS485／MAX3485

- ✅ 已驗證的本機傳輸基準
- 主要本機生命線
- 差動 A／B 傳輸，當現場可提供足夠線芯時優先使用
- 相較單線方案，抗干擾能力與通訊穩健性較有優勢
- 基本門禁路徑不依賴 Internet

## TTL ↔ LIN／TJA1021

- 🧪 替代性單線 PHY
- TJA1021 僅作實體層，不實作完整標準車用 LIN 協議堆疊（protocol stack）
- 上層仍使用本專案自訂的點對點協議（point-to-point protocol）
- 主要目的是支援可用備用線芯有限的既有系統改造／受限配線安裝環境
- 預期只需要一條 LIN 資料線，但仍需要共同 GND 參考
- 硬體驗證待完成

這是為了解決既有多戶型傳統對講機線芯不足的工程替代方向，不是宣稱 LIN 已取代 RS485。公開文件不加入尚未實測的 baud rate、framing、checksum、UART timing、Master／Responder 電氣值、12V／7.5V 結論、SLP wiring、LIN dominant／recessive voltage 或 TXD timeout implementation。

## MQTT

- 🧪 可選的網路傳輸方式；軟體架構與 deterministic validation 已相當完整
- 不取代本機生命線
- Indoor 仍是唯一授權中心
- 部分 live broker／SESSION 驗證證據已存在；最新 lifecycle、broker／ACL 負面案例仍待硬體／網路重新驗證
- broker、username、password、client ID、ACL、Pair ID 與 cryptographic secrets 不公開

## 配線策略邊界

呼叫線再利用不是一種傳輸方式。它只是讓既有導線重新分配；資料仍須選用既有的 RS485、選配 LIN PHY 或 MQTT。高階流程是：既有導線再利用 → 選定傳輸方式 → ButtonEvent 傳遞，不新增第四種傳輸方式。
