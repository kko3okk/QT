# avail\_data\_method\_list

```markup
<avail_data_method_list>
    <avail_data_method id="get_avail_product_group_list" args="" >
        <query_sql use_connection_id="saturn" >select distinct product_group from array_product_t order by product_group </query_sql>
    </avail_data_method>

    <avail_data_method id="get_avail_product_id_list"  args="product_group_list" >
        <query_sql use_connection_id="saturn" >select product_id from array_product_t where product_group in (#product_group_list#) order by product_id</query_sql>
    </avail_data_method>

    <avail_data_method id="get_avail_step_group_list"  >
        <query_sql use_connection_id="saturn" >select distinct step_group from array_step_t order by step_group </query_sql>
    </avail_data_method>

    <avail_data_method id="get_avail_step_id_list"  args="step_group_list" >
        <query_sql use_connection_id="saturn" >select step_id from array_step_t where step_group in (#step_group_list#) order by step_id </query_sql>
    </avail_data_method>
</avail_data_method_list>
```

### avail\_data\_method

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| id |  |  | 用來作為可識別的 ID |
| args |  |  | 目前此參數沒有用 |

#### query\_sql

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| use\_connection\_id |  |  | 輸入的 use\_connection\_id需對應到 &lt;db\_connection\_config&gt; 中定義的 id |

