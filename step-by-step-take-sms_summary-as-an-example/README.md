# Step by step :  以SMS\_SUMMARY為例

以下為已經完成的XML , 呈現在EDA的畫面 ; 接下來為一步步的教學 , 從有到無如何定義出一個QT XML

![](../.gitbook/assets/it.png)

{% code title="SMS\_SUMMARY.xml" %}
```markup
<query_page plugin_db_id="2">
    <criteria_list criteria_seq="c_date_opt,lot_id_list,custom_device_list,step_id_list,param_id_list">
        <criteria id="c_date_opt" view_type="criteria_group" sel_type="radio" is_required="true" label="Date Option" result_args="date_option" next_criteria="#radio_result#">
            <sub_criteria_list>
                <sub_criteria key="c_date_option.past_day" radio_display_name="Past Days" />
                <sub_criteria key="c_date_option.date_range" radio_display_name="Date Range" />
                <!--<sub_criteria key="c_date_option.keyin_component_list" radio_display_name="Key In Glass List"/>-->
            </sub_criteria_list>
        </criteria>
        <criteria id="c_date_option.past_day" view_type="date" is_required="true" label="Past Days" result_args="past_days,past_days_start_hh,past_days_start_mm" next_criteria="custom_type_list">
            <date_opt date_type="past_days" default_value="1" />
            <past_days_opt start_time="00:00" />
        </criteria>
        <criteria id="c_date_option.date_range" view_type="date" is_required="true" label="Date Range" result_args="start_time,end_time" next_criteria="custom_type_list">
            <date_opt date_type="date_range" start_time="07:30" end_time="07:30" />
        </criteria>
        <criteria id="lot_id_list" view_type="key_in" is_required="false" is_support_file_upload="true" label="LOT_ID_LIST" result_args="lot_id_list" next_criteria="custom_type_list">
            <keyin_opt row="10" width="300">
                <desc>please key in Lot id list , separated by ',' or change line.... </desc>
            </keyin_opt>
            <file_upload_opt is_skip_first="true">
                <support_file_type>.csv,.txt</support_file_type>
                <desc>file upload format  , first line : column name , data list from second line
					lot_id
					AALDA-190128	
					AALDA-190129	
				</desc>
            </file_upload_opt>
        </criteria>
        <criteria id="custom_type_list" view_type="select" is_required="false" label="CUSTOM_TYPE" result_args="custom_type_list" next_criteria="prod_id_list">
            <select_opt view_type="multiple" avail_from="avail_data_method" avail_data_method="get_avail_class4_list" />
        </criteria>
        <criteria id="prod_id_list" view_type="select" is_required="false" label="PRODUCT_ID" result_args="prod_id_list" pre_criteria="custom_type_list" next_criteria="custom_device_list">
            <select_opt view_type="multiple" avail_from="avail_data_method" avail_data_method="get_avail_class5_list" />
        </criteria>
        <criteria id="custom_device_list" view_type="select" is_required="false" label="CUSTOM_DEVICE" result_args="custom_device_list" pre_criteria="prod_id_list" next_criteria="step_id_list">
            <select_opt view_type="multiple" avail_from="avail_data_method" avail_data_method="get_avail_class1_list" />
        </criteria>
        <criteria id="step_id_list" view_type="select" is_required="false" label="STEP_ID" result_args="step_id_list" pre_criteria="custom_device_list" next_criteria="param_id_list">
            <select_opt view_type="multiple" avail_from="avail_data_method" avail_data_method="get_avail_class2_list" />
        </criteria>
        <criteria id="param_id_list" view_type="select" is_required="false" label="PARAM_ID" pre_criteria="step_id_list" result_args="param_id_list">
            <select_opt view_type="multiple" avail_from="avail_data_method" avail_data_method="get_avail_class3_list" />
        </criteria>
    </criteria_list>
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
    <avail_data_method_list>
        <avail_data_method id="get_avail_class1_list" args="">
            <query_sql use_connection_id="mssql">SELECT distinct class3 FROM EEAS.dbo.menu_query_item_list where class1 in  (#custom_type_list#) and class2 in  (#prod_id_list#) and functionname='device_info' </query_sql>
        </avail_data_method>
        <avail_data_method id="get_avail_class2_list" args="">
            <query_sql use_connection_id="mssql">SELECT distinct class2 FROM EEAS.dbo.menu_query_item_list where class1 in (#custom_device_list#) and functionname='it_titan_lot_t'  </query_sql>
        </avail_data_method>
        <avail_data_method id="get_avail_class3_list">
            <query_sql use_connection_id="mssql">SELECT distinct class2 FROM EEAS.dbo.menu_query_item_list where class1 in  (#step_id_list#) and functionname='it_titan_lot_summary_t'  </query_sql>
        </avail_data_method>
        <avail_data_method id="get_avail_class4_list">
            <query_sql use_connection_id="mssql">SELECT distinct class1 FROM EEAS.dbo.menu_query_item_list where functionname='device_info'</query_sql>
        </avail_data_method>
        <avail_data_method id="get_avail_class5_list">
            <query_sql use_connection_id="mssql">SELECT distinct class2 FROM EEAS.dbo.menu_query_item_list where class1 in  (#custom_type_list#) and functionname='device_info'  </query_sql>
        </avail_data_method>
    </avail_data_method_list>
    <query_sql use_connection_id="SPARK" mode="plugin_class" class_name="com.tynesys.pti.qt.QTSqlHandler">
        <sql>
			select *
			from  it_titan_lot_t, it_titan_lot_summary_t
			where 1=1 and it_titan_lot_t.step_id = it_titan_lot_summary_t.step_id and it_titan_lot_t.lot_id = it_titan_lot_summary_t.lot_id and it_titan_lot_t.lot_end_time = it_titan_lot_summary_t.lot_end_time #criteria_replace_sql# 
		</sql>
        <column_mapping>
            <column src_col_name="it_titan_lot_t.step_id" data_type="VARCHAR2" display_name="step_id" />
            <column src_col_name="it_titan_lot_t.lot_id" data_type="VARCHAR2" display_name="lot_id" />
            <column src_col_name="it_titan_lot_t.equip_id" data_type="VARCHAR2" display_name="equip_id" />
            <column src_col_name="it_titan_lot_t.recipe_name" data_type="VARCHAR2" display_name="recipe_name" />
            <column src_col_name="it_titan_lot_t.custom_device" data_type="VARCHAR2" display_name="custom_device" />
            <column src_col_name="it_titan_lot_t.lot_start_time" data_type="DATE" display_name="lot_start_time" />
            <column src_col_name="it_titan_lot_t.lot_end_time" data_type="DATE" display_name="lot_end_time" />
            <column src_col_name="it_titan_lot_t.inspected_count" data_type="NUMBER" display_name="inspected_count" />
            <column src_col_name="it_titan_lot_t.accepted" data_type="NUMBER" display_name="accepted" />
            <column src_col_name="it_titan_lot_t.rejected" data_type="NUMBER" display_name="rejected" />
            <column src_col_name="it_titan_lot_t.yield" data_type="NUMBER" display_name="yield" />
            <column src_col_name="it_titan_lot_t.update_time" data_type="DATE" display_name="update_time" />
            <column src_col_name="it_titan_lot_t.cancel_lot_flag" data_type="VARCHAR2" display_name="cancel_lot_flag" />
            <column src_col_name="it_titan_lot_t.current_location" data_type="VARCHAR2" display_name="current_location" />
            <column src_col_name="it_titan_lot_t.data_year_start" data_type="NUMBER" display_name="data_year_start" />
            <column src_col_name="it_titan_lot_t.data_year_end" data_type="NUMBER" display_name="data_year_end" />
            <column src_col_name="it_titan_lot_t.create_time" data_type="DATE" display_name="create_time" />
            <column src_col_name="it_titan_lot_t.data_year" data_type="VARCHAR2" display_name="data_year" />
            <column src_col_name="it_titan_lot_summary_t.param_collection" data_type="VARCHAR2" display_name="param_collection" />
            <column src_col_name="it_titan_lot_summary_t.param_id" data_type="VARCHAR2" display_name="param_id" />
            <column src_col_name="it_titan_lot_summary_t.data_month_end" data_type="VARCHAR2" display_name="data_month_end" />
            <column src_col_name="it_titan_lot_summary_t.data_month_start" data_type="VARCHAR2" display_name="data_month_start" />
            <column src_col_name="it_titan_lot_summary_t.def_code_name" data_type="VARCHAR2" display_name="def_code_name" />
            <column src_col_name="it_titan_lot_summary_t.defect_count" data_type="NUMBER" display_name="defect_count" />
            <column src_col_name="it_titan_lot_summary_t.data_year" data_type="VARCHAR2" display_name="data_year" />
        </column_mapping>
    </query_sql>
    <db_connection_config>
        <connection id="oracle" type="from_tyne_plugin_db_t" plugin_db_id="1" />
        <connection id="mssql" type="from_tyne_plugin_db_t" plugin_db_id="3" />
    </db_connection_config>
</query_page>
```
{% endcode %}

