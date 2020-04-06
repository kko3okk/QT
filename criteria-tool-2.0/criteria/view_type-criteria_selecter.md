# view\_type="criteria\_selector"

```markup
 <criteria id="criteria_selector"  view_type="criteria_selector" is_required="false" label="過濾條件" button_label="Add+" group="1">
		<selector_opt value="equip_ID" display_name="EQP ID"/>
       <select_opt avail_from="avail_data_method" avail_data_method="get_avail_class8_list"  />
    </selector_opt>
    <selector_opt value="lot_type" display_name="LOT_TYPE ID"/>
       <select_opt avail_from="avail_data_method" avail_data_method="get_avail_class8_list"  />
    </selector_opt>
</criteria>
```

![view\_type=&quot;criteria\_selector&quot;](../../.gitbook/assets/image-8%20%281%29.png)

### Criteria

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| button\_label |  | ex : Add+ | 定義Button顯示的名稱 ; 預設值=Add+ |
| dialog\_label |  |  | 定義燈箱Title的名稱 |

### selector\_opt

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| value |  |  |  |
| display\_name |  |  | UI顯示名稱 |
| fk\_selected |  | keep/filter | 預設值為keep, 代表選擇\(K\) |

### select\_opt

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| avail\_from |  | constants / avail\_data\_method | 相關說明與[select](view_type-select/)相同 |
| avail\_data\_method |  |  |  |

