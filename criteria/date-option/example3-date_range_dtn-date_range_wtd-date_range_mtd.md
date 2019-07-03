# example3 : date\_range\_\*

```markup
<criteria id="c_date_opt" view_type="criteria_group" sel_type="radio" is_required="true" label="Date Option" result_args="date_option" next_criteria="#radio_result#" > 
    <sub_criteria_list>
        <sub_criteria key="c_date_option.date_range_DTN"   radio_display_name="DTN"  />
        <sub_criteria key="c_date_option.date_range_WTD"   radio_display_name="WTD"  />
        <sub_criteria key="c_date_option.date_range_MTD"   radio_display_name="MTD"  />                            
    </sub_criteria_list>
</criteria>                                                                                                              
<criteria id="c_date_option.date_range_DTN" view_type="date" is_required="true" label="DTN" visiablity="hidden" result_args="DTN_start_date,DTN_start_hhmm,DTN_end_date,DTN_end_hhmm" next_criteria="product_group_list">
        <date_opt date_type="date_range_DTN"  start_date="today"  start_hhmm="07:30" end_date="today" end_hhmm="now"   />            
        <criteria_sql>glass_start_time between #DTN_start_time# and #DTN_end_time# </criteria_sql>
</criteria>
<criteria id="c_date_option.date_range_WTD" view_type="date" is_required="true" label="WTD"  visiablity="hidden" result_args="WTD_start_date,WTD_start_hhmm,WTD_end_date,WTD_end_hhmm" next_criteria="product_group_list">
        <date_opt   date_type="date_range_WTD"  start_date="monday" start_hhmm="07:30" end_date="today" end_hhmm="07:30"   />            
        <criteria_sql>glass_start_time between #WTD_start_time# and #WTD_end_time# </criteria_sql>
</criteria>
<criteria id="c_date_option.date_range_MTD" view_type="date" is_required="true" label="MTD" visiablity="hidden" result_args="MTD_start_date,MTD_start_hhmm,MTD_end_date,MTD_end_hhmm" next_criteria="product_group_list">
        <date_opt    date_type="date_range_MTD"  start_date="1_of_month" start_hhmm="07:30" end_date="today" end_hhmm="07:30"   />            
        <criteria_sql>glass_start_time between #MTD_start_time# and #MTD_end_time# </criteria_sql>
</criteria>
```

```markup
<arg name="WTD_start_date"         from_id="c_date_option.date_range_WTD"       data_type="string"  />
<arg name="WTD_start_hhmm"         from_id="c_date_option.date_range_WTD"       data_type="string"  />
<arg name="WTD_end_date"           from_id="c_date_option.date_range_WTD"       data_type="string"  />
<arg name="WTD_end_hhmm"           from_id="c_date_option.date_range_WTD"       data_type="string"  />
<arg name="WTD_start_time"         from_id="c_date_option.date_range_WTD"       data_type="date" format="yyyymmddhh24miss" />
<arg name="WTD_end_time"           from_id="c_date_option.date_range_WTD"       data_type="date" format="yyyymmddhh24miss" />

<arg name="MTD_start_date"         from_id="c_date_option.date_range_MTD"       data_type="string"  />
<arg name="MTD_start_hhmm"         from_id="c_date_option.date_range_MTD"       data_type="string"  />
<arg name="MTD_end_date"           from_id="c_date_option.date_range_MTD"       data_type="string"  />
<arg name="MTD_end_hhmm"           from_id="c_date_option.date_range_MTD"       data_type="string"  />
<arg name="MTD_start_time"         from_id="c_date_option.date_range_MTD"       data_type="date" format="yyyymmddhh24miss" />
<arg name="MTD_end_time"           from_id="c_date_option.date_range_MTD"       data_type="date" format="yyyymmddhh24miss" />
```

