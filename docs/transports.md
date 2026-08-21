# Transports

## RS485／MAX3485

- ✅ validated baseline
- 主要 local lifeline
- UART-based local transport
- 不依賴 Internet 才能完成基本門禁路徑

## TTL ↔ LIN／TJA1021

- 🧪 alternative single-wire physical layer
- TJA1021 僅作 PHY，不使用完整標準 automotive LIN protocol stack
- 上層仍採本專案的 point-to-point／LIN-like transport direction
- 目標是 spare conductors 有限的傳統多戶型對講機安裝環境
- hardware validation pending

本公開文件不宣稱 baud rate、framing、checksum、timing、master wiring 或電氣實測結論。

## MQTT

- 🧪 optional network transport
- 不取代 RS485 local lifeline
- Indoor 仍是 authorization authority
- broker、username、password、client ID、ACL、Pair ID 與 cryptographic secrets 不公開
