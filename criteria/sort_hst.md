# sort\_hst

```markup
<criteria id="sort_hst"  view_type="sort_hst" is_required="false" label="Sort Area" pre_criteria="step_id_list">
    <sort_hst  sort_hst_key="array_glass_hst" src_join_column="array_glass_id"  />
    <sort_hst  sort_hst_key="cell2_chip_hst" src_join_column="chip_id"  />
</criteria>
```

### sort\_hst

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| sort\_hst\_key | V |  | 對應到**sort\_hst\_define**的key value |
| src\_join\_column | V |  | 來源資料要被join的欄位 |

```markup
<sort_hst_define>
    <sort_hst  sort_hst_key="array_glass_hst" display_name="Array Glass History">
        <sort_hst_query_opt  join_column="glass_id"    />
        <avail_step_sql use_connection_id="saturn">
            select step_id from array_step_t
        </avail_step_sql>
        <avail_item_list> 
                <column src_col_name="glass_id" data_type="VARCHAR2" display_name="glass_id"  />
                <column src_col_name="equip_id" data_type="VARCHAR2" display_name="equip_id"  />
                <column src_col_name="glass_start_time" data_type="DATE" display_name="glass_start_time"  />
        </avail_item_list>
        <time_sql use_connection_id="saturn">
                select min(data_start_time) as start_time , max(data_end_time) as end_time from array_cmn_glass_t where glass_id in (#SRC_JOIN_ID_LIST#) 
        </time_sql>
        <sql use_connection_id="saturn">
                select * from array_glass_hst_t where step_id in (#SORT_STEP_LIST#) and  glass_start_time between #START_TIME# and #END_TIME# 
        </sql>
    </sort_hst>

    <sort_hst  sort_hst_key="cell2_chip_hst" display_name="Cell2 Chip History">
        <sort_hst_query_opt  join_column="chip_id"    />
        <avail_step_sql use_connection_id="saturn">
            select step_id from cell2_step_t
        </avail_step_sql>
        <avail_item_list> 
                <column src_col_name="chip_id" data_type="VARCHAR2" display_name="chip_id"  />
                <column src_col_name="equip_id" data_type="VARCHAR2" display_name="equip_id"  />
                <column src_col_name="chip_start_time" data_type="DATE" display_name="chip_start_time"  />
        </avail_item_list>
        <time_sql use_connection_id="saturn">
                select min(data_start_time) as start_time , max(data_end_time) as end_time from cell2_cmn_chip_t where glass_id in (#SRC_JOIN_ID_LIST#) 
        </time_sql>
        <sql use_connection_id="saturn">
                select * from cell2_chip_hst_t where step_id in (#SORT_STEP_LIST#) and  chip_start_time between #start_time# and #end#
        </sql>
    </sort_hst>
</sort_hst_define>
```

{% hint style="info" %}
後續會提供出一版base Sort Hst xml 做使用
{% endhint %}

### sort\_hst

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| sort\_hst\_key | V |  | key value |
| display\_name | V |  | 顯示於UI的名稱 |

### sort\_hst\_query\_opt

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| join\_column | V |  | 被串接資料源, join的欄位名稱 |

### avail\_step\_sql

#### 元件上取得step\_id 的sql編寫

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| use\_connection\_id | V |  | 使用connection id |

### avail\_item\_list

原件上取得item\_list ; 目前為定義出現哪些欄位

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
|  |  |  |  |

### time\_sql

取得sql要使用的時間欄位 , **start\_time &  end\_time** 為必要欄位名稱

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| use\_connection\_id | V |  | 使用connection id |

### sql

query 串接資料的sql 

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| use\_connection\_id | V |  | 使用connection id |

