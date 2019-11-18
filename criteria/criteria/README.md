# Criteria

```markup
<criteria id="c_date_opt" view_type="criteria_group" sel_type="radio" 
is_required="true" label="Date Option" result_args="date_option" 
next_criteria="#radio_result#" >
........
</criteria>
```

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| id | V |  | 自行定義可識別 criteria 的 ID |
| view\_type | V |  |  |
|  |  | [criteria\_group](../criteria-group/) |  |
|  |  | [date](../date-option/) |  |
|  |  | [key\_in](../key-in/) |  |
|  |  | [select](../select/) |  |
|  |  | [checkbox](../checkbox/) |  |
|  |  | [radio](../radio-button.md) |  |
|  |  | [merge\_column\_picker](../merge_column_picker.md) |  |
|  |  | [sort\_hst](../sort_hst.md) |  |
| is\_required | V | true / false |  |
| label | V |  | 自行定義要顯示在UI  畫面的 Criteria 名稱 |
| result\_args | V |  | 自行宣告該 Criteria 輸出的變數名稱，該變數名稱，將對應到&lt;global\_arfs\_define&gt; 中的  arg\_name |
| pre\_criteria |  |  | 填入相依的前一個 Criteira ID |
| next\_criteria |  |  | 填入 UI 畫面要出現的下一個 Criteria ID \(**使用criteria\_group的時候沒有用**\) |
| mode |  | OLD / AS\_CRITERIA | 控制支援模式 |
| is\_support\_file\_upload |  | true / false |  |
| is\_support\_all\_flag |  | true / false | 控制選項是否出現ALL Button |
| all\_flag\_var |  | ex : param\_name\_list\_all | 紀錄all flag是否開啟的參數 |
| visiablity |  | hidden | 若設定 visiablity="hidden"，表示該 criteria 隱藏不顯示。 目前提供此屬性的 criteria 有 : DTN、WTD、MTD |
| sel\_type |  | [all ](../criteria-group/expand_or_collapse.md)/ radio / check | all :全部sub criteria 都直接出現 \(default\)        radio : 多選一                                                      check : 多選N 模式 |
| default\_expand |  | true / false | sel\_type= all 才有作用 |



