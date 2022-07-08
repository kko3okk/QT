# Criteria

{% hint style="warning" %}
1\. 需要Review 目前有哪些元件 ; 以及內容是否有作修改

2\. ui\_group\_style 命名需要定義 (Wen會提供class名稱)

3.T7 DS 畫面 , 目前html是不同一份 (需要再確認 )  ; 顏色/展開 是否能用設定控制 (OK)
{% endhint %}

| Attributes                         | Required | Parameters                         | Description                                                                                                       |
| ---------------------------------- | -------- | ---------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| id                                 | V        |                                    | 重要 !!  第一群擷取日期的radio group, 沒有使用plugin\_class時 , id請固定叫 : c\_date\_opt ; Prod code認字眼做事情                          |
| view\_type                         | V        | ui\_group                          | UI上呈現的分群                                                                                                          |
|                                    |          | [checkbox](view\_type-checkbox.md) |                                                                                                                   |
|                                    |          | [radio](view\_type-radio.md)       |                                                                                                                   |
|                                    |          | [date](view\_type-date.md)         |                                                                                                                   |
|                                    |          | [keyin](view\_type-key\_in/)       |                                                                                                                   |
| is\_required                       |          |                                    | 預設值 = false                                                                                                       |
| label                              |          |                                    | 沒輸入代表元件前不顯示Label                                                                                                  |
| result\_args                       |          |                                    | 可不定義 (系統自動產生)                                                                                                     |
| pre\_criteria\_logic               |          | and/or                             | 預設值=and                                                                                                           |
| pre\_criteria                      |          |                                    | <p>請參考下半部 pre_criteria 處理邏輯</p><p>pre_criteria="ABC"  ->  ABC.result</p><p>pre_criteria="ABC.abc"  -> ABC.abc</p> |
| next\_criteria                     |          |                                    | next\_criteria="tab\_condition" , next\_criteria="#radio\_result#"                                                |
| group                              |          |                                    | 舉例 :  兩個criteria都設定group="1" , 就會被放在同一行 ; 值只要相同就可 , 但要連續的才會被判斷成同一行                                                |
| pre\_criteria\_from(old)           |          |                                    | ex : 找到上一層的pre\_criteria來源                                                                                        |
| pre\_criteria\_next(old)           |          |                                    | 找到上一層的next\_criteria                                                                                              |
| pre\_criteria\_value\_specify(old) |          |                                    | ex : 預設拿result , 可指定其他值, 例如 : is\_base\_by                                                                        |
| pre\_criteria\_value\_is(old)      |          |                                    | 判斷式 , = "ture"                                                                                                    |

{% hint style="info" %}
請參考下半部 pre\_criteria 處理邏輯 (version=2.1)

_pre\_criteria_="data\_type"   -> data\_type 只要是任意值 , 即可通過

pre\_criteria="ABC,DEF=123|456"    ->  DEF的值只要符合123 or 456 , 即可通過

pre\_criteria="ABC,DEF\&test123=123|456"    ->  DEF.test123的值只要符合123 or 456 , 即可通過

pre\_criteria="ABC,DEF=123&456"   -> DEF的值要同時符合123 and 456 , 才能通過
{% endhint %}
