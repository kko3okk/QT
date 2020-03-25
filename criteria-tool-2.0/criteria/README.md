# Criteria

{% hint style="warning" %}
1. 需要Review 目前有哪些元件 ; 以及內容是否有作修改

2. ui\_group\_style 命名需要定義 \(Wen會提供class名稱\)

3.T7 DS 畫面 , 目前html是不同一份 \(需要再確認 \)  ; 顏色/展開 是否能用設定控制 \(OK\)
{% endhint %}

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| id | V |  |  |
| view\_type | V | ui\_group | UI上呈現的分群 |
|  |  | [checkbox](view_type-checkbox.md) |  |
|  |  | [radio](view_type-radio.md) |  |
|  |  | [date](view_type-date.md) |  |
|  |  | [keyin](view_type-key_in/) |  |
| is\_required |  |  | 預設值 = false |
| label |  |  | 沒輸入代表元件前不顯示Label |
| result\_args |  |  | 可不定義 \(系統自動產生\) |
| pre\_criteria |  |  | pre\_criteria="data\_type" |
| next\_criteria |  |  | next\_criteria="tab\_condition" , next\_criteria="\#radio\_result\#" |
| group |  |  | 舉例 :  兩個criteria都設定group="1" , 就會被放在同一行 ; 值只要相同就可 , 但要連續的才會被判斷成同一行 |
| pre\_criteria\_value\_is |  |  |  |


