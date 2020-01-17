# 優化

* global\_args\_define 全面移除
  * 代表criteria 裡面的result\_args將被移除 , 改由\[criteria\_id\].\[naming\_rule\] 和 文件來支持各元件的參數
* 與global\_args\_define 相關的功能 \(ex : default\_value & format\) , 需要評估要搬到哪個地方
* 確認繼承機制
* 減少QT部署時 , 人工維護DataBase的相關動作
* QT前端顯示元件的順序
* 日期格式處理的PROD化
* Load XML to memory vs Load File
* 目前使用QT全部XML都會被讀取一次 , 希望改成用哪一隻讀哪一隻XML
* 美工  \(思考Layout - 如何提供設定 , 顯示畫面\)
* 元件之間getAvailable 的相依姓 
* QT前端如何更準確顯示Error Message, 或者更有系統性的管理錯誤訊息
* 效能優化 \(優化available 抓取的時機 \) 
  * select 元件目前取大量數據時 , 會有效能問題 , 需討論是否有改進處







