# 已知問題 , 待修復

* result\_arg 要可以沿用 , 不然QT1.0升級到QT2.0還要做XML的修改
* without plugin\_class , 自動組合SQL的value判斷 , 需要做修改 ; 不然使用自動生成的Arg\_map都會有問題



12/3 : 

* fetch data之前, 要先檢查欄位是否都存在\(Eric惠提供解法\)
* data\_column\_picker : 要討論沒有選擇時, 是否初始化就要選到左邊, 讓User知道是全選\(Mac提議, 現況會讓User不知道是全選\)
* Peter表示:後續繼承看能不能繼承多個XML,  想辦法讓ET\_QT可以不需要duplicate
* 
