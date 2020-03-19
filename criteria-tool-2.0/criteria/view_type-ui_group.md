# view\_type="ui\_group"

### Criteria

| Attributes | Required | Parameters | Description | Support css |
| :--- | :--- | :--- | :--- | :--- |
| ui\_group\_style | V | 1/2/3/4 | 決定使用何種樣式 |  |
| ui\_color |  |  | 定義group背景顏色 | 1/6 |
| ui\_group\_type |  | expand\_or\_collapse | 決定group是否能夠縮合 | 1/5 |
| ui\_group\_default\_expand |  |  | ui\_group\_type="expand\_or\_collapse" , 設定縮合的初始狀態, 預設值true | 1/5 |

![](../../.gitbook/assets/image-9.png)

### tab\_opt

{% hint style="info" %}
ui\_group\_style="4"的時候才需要被定義
{% endhint %}

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| id |  |  |  |
| label |  |  | tab上顯示的名稱 |

