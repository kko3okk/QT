---
description: '規範新需求 & 出Patch時 , QT Owner 需要自我測試的項目'
---

# QT測試項目



| 項目 | 說明 |
| :--- | :--- |
| interactive | 挑選任一 QT DS, 選擇條件撈出資料 |
| save preference | 根據上一步驟的interactive , 存成preference |
| test preference : load & run | 測試preference  , 執行load & run \(ps 必須都執行過一次, 因為程式邏輯不相同\) |
| ----------------------------------------------- | **以下為第一次上半時才需要測試** |
| set schedule job | 將上一步驟的preference設定成schedule job \(Quartz or Oracle擇一\) |
| check schedule  result | 確認schedule job執行完畢 , 並且檢查解果是否有產生 |



