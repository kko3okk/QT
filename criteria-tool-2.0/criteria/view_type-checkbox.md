# view\_type="checkbox"

```markup
<criteria id="c_is_include_retest"  view_type="checkbox" is_required="false" label="重工/重测"  result_args="is_include_old_data">
    <checkbox_opt check_type="single">
        <check_item value="TRUE"  display_name="include rework/retest" default_check="true" />
    </checkbox_opt>
    <criteria_sql mode="logic">
        <when_null arg="is_include_old_data" >
                <sql>array_glass_t.ITEM7 ='V'</sql>
        </when_null>
        <equals   arg="is_include_old_data" value="TRUE">
        </equals>    
     </criteria_sql>
</criteria>

```

```markup
<criteria id="HST"  view_type="checkbox" is_required="false" result_args="hst_result" pre_criteria="data_type" next_criteria="tab_condition">
	<checkbox_opt check_type="multi" is_support_base_by="true">
		<check_item value="array_glass_his"  display_name="Array Glass History" default_check="true" />
		<check_item value="cf_glass_his"  display_name="CF Glass History" />
		<check_item value="cell_component_his"  display_name="Cell Component History"/>
		<check_item value="cell2_panel_his"  display_name="Cell2 Panel History"/>
	</checkbox_opt>
</criteria>
```

### Criteria

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
|  |  |  |  |

### checkbox\_opt

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| check\_type | V | single / multi | single 只顯示第一個check\_item |
| max\_count |  |  | 最多被選擇的數量 |
| is\_support\_base\_by |  | true/ false | UI是否顯示base by |
| support\_base\_by\_selected |  | true/ false | 預設值 = true |

![is\_support\_base\_by](../../.gitbook/assets/image-6.png)

#### check\_item

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| value | V |  |  |
| display\_name | V |  |  |
| default\_check |  | true / false | 預設值false |

### criteria\_sql

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| mode |  |  |  |

#### when\_null

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| arg |  |  |  |

#### equals

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| arg |  |  |  |
| value |  |  |  |

