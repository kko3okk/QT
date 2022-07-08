# Step2 : global\_args\_define

完成第一步之後 , 需要確認criteria的變數存放是否都有設定到 , 例如

```markup
<criteria id="param_id_list" view_type="select" is_required="false" label="PARAM_ID" pre_criteria="step_id_list" result_args="param_id_list">
    <select_opt view_type="multiple" avail_from="avail_data_method" avail_data_method="get_avail_class3_list" />
</criteria>
```

其中Criteria Attributes - result\_args , **其意義為該元件選擇值以後 , 被選擇的值要存放到哪一個變數** ; **** 所以以一句話來說 : Criteria 使用到的 result\_args都必須被定義在global\_args\_define&#x20;

```markup
 <global_args_define>
        <arg name="date_option" from_id="c_date_opt" data_type="string" />
        <arg name="past_days" from_id="c_date_option.past_day" data_type="number" />
        <arg name="past_days_start_hh" from_id="c_date_option.past_day" data_type="string" />
        <arg name="past_days_start_mm" from_id="c_date_option.past_day" data_type="string" />
        <arg name="start_time" from_id="c_date_option.date_range" data_type="date" format="yyyyMMddHHmm" />
        <arg name="end_time" from_id="c_date_option.date_range" data_type="date" format="yyyyMMddHHmm" />
        <arg name="week_no" from_id="c_date_option.week" data_type="string" />
        <arg name="month_no" from_id="c_date_option.month" data_type="string" />
        <arg name="lot_id_list" from_id="lot_id_list" data_type="string_array" />
        <arg name="custom_type_list" from_id="custom_type_list" data_type="string_array" />
        <arg name="prod_id_list" from_id="prod_id_list" data_type="string_array" />
        <arg name="custom_device_list" from_id="custom_device_list" data_type="string_array" />
        <arg name="step_id_list" from_id="step_id_list" data_type="string_array" />
        <arg name="param_id_list" from_id="param_id_list" data_type="string_array" />
</global_args_define>
```
