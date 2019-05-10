# global\_args\_define

```markup
<global_args_define>
        <arg name="date_option"        	from_id="c_date_opt"                     	data_type="string" />
        <arg name="past_days"          	from_id="c_date_option.past_day"         	data_type="number" />
        <arg name="past_days_start_hh"  from_id="c_date_option.past_day"         	data_type="string" />
        <arg name="past_days_start_mm"  from_id="c_date_option.past_day"         	data_type="string" />
        <arg name="start_time"         	from_id="c_date_option.date_range"       	data_type="date" format="yyyyMMddHHmm" />
        <arg name="end_time"           	from_id="c_date_option.date_range"       	data_type="date" format="yyyyMMddHHmm" />
        <arg name="week_no"  from_id="c_date_option.week"             data_type="string" />
        <arg name="month_no"  from_id="c_date_option.month"             data_type="string" />
        <arg name="sbt_id_list"     	from_id="sbt_id_list"         			data_type="string_array"  />
        <arg name="step_id_list"     	from_id="step_id_list"         			data_type="string_array"  />
        
        <arg name="sbt_id_list.source_data_set_id" from_id="source_data_set_distinct_data"          data_type="string" />
        <arg name="sbt_id_list.column_name" from_id="source_data_set_distinct_data"                 data_type="string"  />
        <arg name="sbt_id_list.distinct_data_list" from_id="source_data_set_distinct_data"          data_type="string_array"  />
        
        <arg name="fuseid_list.source_data_set_id" from_id="source_data_set_distinct_data"          data_type="string" />
        <arg name="fuseid_list.column_name" from_id="source_data_set_distinct_data"                 data_type="string"  />
        <arg name="fuseid_list.distinct_data_list" from_id="source_data_set_distinct_data"          data_type="string_array"  />
        
        <arg name="d2id_list.source_data_set_id" from_id="source_data_set_distinct_data"          data_type="string" />
        <arg name="d2id_list.column_name" from_id="source_data_set_distinct_data"                 data_type="string"  />
        <arg name="d2id_list.distinct_data_list" from_id="source_data_set_distinct_data"          data_type="string_array"  />
</global_args_define>
```

### arg

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| name | V |  | name 的名稱需對應到 &lt;criteria&gt; Tag 的result\_args |
| from\_id | V |  | from\_id 填入的值，須為某一個criteria 的ID。 |
| data\_type | V | string/ string\_array/ date |  |
| format |  |  | 當 data\_type=”date” 時，需定義format |
| data\_value |  |  | 用來定義變數預設值, 一般不需要定此屬性, 會定義此data\_value 通常是拿來當作常數用 |

