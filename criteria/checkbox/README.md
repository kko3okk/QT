# CheckBox

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

### checkbox\_opt

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| check\_type | V | single / multi | single 只顯示第一個check\_item |
| max\_count |  |  | 最多被選擇的數量 |

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

