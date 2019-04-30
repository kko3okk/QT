# Step3 : 撈取資料

上述步驟完成後 , 實作Query的動作

```markup
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
```

### query\_sql

1. 模式為plugin\_class
2. class的路徑在 com.tynesys.pti.qt.QTSqlHandler

```markup
<query_sql use_connection_id="SPARK" mode="plugin_class" class_name="com.tynesys.pti.qt.QTSqlHandler">
```

### sql

到哪個Table撈資料 , select 的值會根據**column\_mapping**動態組出來 , 因此基本格式為

```sql
select *
from  [table_name]
where [condition] #criteria_replace_sql# 
```

plugin\_class處理criteria的條件之後 ,  取代上述SQL中的

```sql
#criteria_replace_sql#
```

最後就會用該語法到資料庫撈取資料

