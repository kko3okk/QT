# view\_type="radio"



```markup
<criteria id="data_type" view_type="radio" ui_group_style="button" label="數據類型" result_args="data_type" next_criteria="#radio_result#">
	<radio_opt>
		<radio_item value="HST"  display_name="HST" default_check="true" />
		<radio_item value="DEFECT"  display_name="DEFECT" />
		<radio_item value="EDC"  display_name="EDC" />
		<radio_item value="PDS"  display_name="PDS" />
	</radio_opt>
</criteria>
```

### Criteria

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| ui\_group\_style |  | radio/button | 預設值 = radio ; 樣式show為Button |
| next\_criteria |  | \#radio\_result\# | 根據Raid的Valeu, 動態替換值 |

![ui\_group\_style=&quot;button&quot;](../../.gitbook/assets/image-7.png)

### radio\_opt

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| default\_selected\_first |  | true/false | 預設值=true |
| enable\_cancel\_selected |  | true/false | 預設值=false |

#### radio\_item

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| value | V |  | 真正值 |
| display\_name | V |  | UI顯示值 |
| default\_check |  | true / false | 預設值為false |

