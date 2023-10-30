# example4 :使用source dataset 取max/min date value

```markup
<criteria id="c_date_option.date_range" view_type="date" is_required="true" label="Date Range"  result_args="start_time,end_time" next_criteria="equip_group_list">
    <date_opt date_type="date_range" is_support_source_data_set=”true” />
</criteria>          
```

注意 , 有使用is\_support\_source\_data\_set , 必須在 global\_args\_define 加入以下三個變數 (否則會報錯) :

\[criteria-id].source\_data\_set\_id \
\[criteria-id].date\_column\_name \
\[criteria-id].min\_max\_time\_pair

```
<global_args_define>
        <arg name="c_date_option.date_range.source_data_set_id" from_id="source_data_set_distinct_data" data_type="string" />
        <arg name="c_date_option.date_range.date_column_name" from_id="source_data_set_distinct_data" data_type="string"  />
        <arg name="c_date_option.date_range.min_max_time_pair" from_id="source_data_set_distinct_data" data_type="string_array"  />
</global_args_define>
```
