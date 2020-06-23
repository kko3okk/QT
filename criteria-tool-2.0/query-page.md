# Query page

```markup
<query_page base_query_tool_id="base" disable_save_button="true">
....
</query_page>
```

```markup
<query_page plugin_db_id="2" forward_url="/eeas-rest/setup/SPCIndicator/main" route_url="#/eeas/setting/setup/detail">
........
</query_page>
```

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| base\_query\_tool\_id |  |  | 繼承XML的名稱 |
| disable\_save\_button |  | true / false | 顯示 / 隱藏 save button |
| forward\_url |  |  | 導向目標網址 |
| route\_url |  |  | 與forward\_url配對 |
| enable\_help\_icon |  | true / false | 預設值為false \(not ready\) |
| help\_file\_location |  |  | help file放置的路徑 \(not ready\) |
| mode\_type |  | new\_ds/old\_ds | 提供程式判斷使用什麼樣式 , 預設值=old\_ds |
| enable\_i18n |  | true / false | 預設值=false |
| query\_by\_pluginclass |  | true / false | 預設值=false |
| query\_tool\_version |  | QT1/QT2 | 預設值 = QT1 |
| pre\_criteria\_version |  | QT2/QT2.1 | 預設值 = QT2 , 走原本的pre\_criteria邏輯  ; QT2.1 , 可設定pre\_criteria display logic |
| is\_support\_analysis\_preference |  | true/ false | 先判斷TYNE\_CONFIG\_T有沒有定義is\_support\_analysis\_preference ; 有的話XML的設定值無效 , 預設值=true |
|  |  |  |  |

