# Radio Button

```markup
<criteria id="radio_id"  view_type="radio" is_required="false" label="RADIO EXAMPLE"  result_args="radio_value">
    <radio_opt>
        <radio_item value="TEST1"  display_name="A" default_check="true" />
		<radio_item value="TEST2"  display_name="B" />
		<radio_item value="TEST3"  display_name="C" />
    </radio_opt>
</criteria>
```

### radio\_opt

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
|  |  |  |  |

#### radio\_item

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| value | V |  | 真正值 |
| display\_name | V |  | UI顯示值 |
| default\_check |  | true / false | 預設值為false |

