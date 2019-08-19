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
<sort_hst_define id="type" label="Sort Area Type">
    <sort_hst  sort_hst_key="array_glass_hst" display_name="Array Glass History">
        <sort_hst_query_opt  join_column="glass_id"    />
        
        <criteria id="step_id_list" view_type="select" is_required="false" label="STEP_ID">
            <select_opt view_type="multiple" avail_from="avail_data_method" avail_data_method="get_avail_step_id_list" />
        </criteria>
        
        <criteria id="item_list"  view_type="select" is_required="false" label="ITEM LIST">
        	<select_opt view_type="multiple" avail_from="constants" />
        	<avail_constants>glass_id,equip_id,chip_start_time</avail_constants>
        </criteria>
        
        <time_sql use_connection_id="saturn">
                select min(data_start_time) as start_time , max(data_end_time) as end_time from array_cmn_glass_t where glass_id in (#SRC_JOIN_ID_LIST#) 
        </time_sql>
        
        <sql use_connection_id="saturn">
                select * from array_glass_hst_t where step_id in (#SORT_STEP_LIST#) and  glass_start_time between #START_TIME# and #END_TIME# 
        </sql>
    </sort_hst>
</sort_hst_define>


<avail_data_method_list>
    <avail_data_method id="get_avail_step_id_list">
        <query_sql use_connection_id="saturn" >select step_id from array_step_t </query_sql>
    </avail_data_method>
</avail_data_method_list>


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

