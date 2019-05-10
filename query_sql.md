# query\_sql

```markup
<query_sql use_connection_id="SPARK" mode="plugin_class" class_name="com.tynesys.chot.qt.QTSqlHandler">
    <sql>
    select glass_id ,step_id, glass_start_time, product_id, equip_id , item1 as lot_id 
    from array_glass_t, array_step_t 
    where array_step_t.step_id = array_glass_t.step_id #criteria_replace_sql# order by glass_start_time
    </sql>
    <column_mapping>
        <column src_col_name="array_glass_t.glass_id" data_type="VARCHAR2" display_name="glass_id"  />
        <column src_col_name="array_glass_t.step_id" data_type="VARCHAR2" display_name="step_id"  />
        <column src_col_name="array_glass_t.glass_start_time" data_type="DATE" display_name="glass_start_time"  />            
        <column src_col_name="array_glass_t.product_id" data_type="VARCHAR2" display_name="product_id"  />
        <column src_col_name="array_glass_t.equip_id" data_type="VARCHAR2" display_name="equip_id"  />
        <column src_col_name="array_glass_t.item1" data_type="VARCHAR2" display_name="lot_id"  />  
    </column_mapping>
</query_sql>
```

### query\_sql

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| use\_connection\_id | V |  |  |
| mode |  | plugin\_class/  |  |
| class\_name |  |  |  |
| plugin\_opt |  |  |  |

#### sql

編輯點GO之後做的動作

#### column\_mapping

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| mode |  | eda\_lookup/  |  |
| is\_need\_pre\_process\_arg\_map |  |  |  |

#### **eda\_lookup\_opt**

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| lookup\_mode |  | datapath**/**table\_list |  |
| datapath |  |  |  |
| table\_list |  |  |  |

#### column

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| src\_col\_name | V |  |  |
| data\_type | V | VARCHAR2/ DATE/ NUMBER |  |
| display\_name | V |  |  |



