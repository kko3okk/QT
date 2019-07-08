# 需求清單

## "QueryTool 選項 \[Column to Query Data\] 要能預選機制

1. 實現base.xml 功能 : 全部tag都需要支援

* 繼承  -&gt;  後蓋前 \(本地  &gt;  global\)

2. 變數的替代 , 會在global\_args\_define定義

```markup
<global_args_define>
    <arg name="product_name"     defult_value="array_glass_t" />
</global_args_define>
```

接著我可以在以下做替換 :

```markup
<column_mapping>
	<column src_col_name="#product_name#.step_group"  			data_type="VARCHAR2" 	           display_name="step_group" />			
</column_mapping>
```

或者是在is\_support\_source\_data\_set\_opt 新增預選變數

```markup
<criteria id="lot_id_list" view_type="key_in" is_required="false" is_support_file_upload="true" label="Lot ID List" result_args="lot_id_list" next_criteria="current_location_list">
	<keyin_opt row="10" width="300" is_support_source_data_set="true">
	<source_data_set_opt>#product_name#</source_data_set_opt>
		<desc>please key in LOT id list , separated by ',' or change line.... </desc>
	</keyin_opt>						
	<file_upload_opt  is_skip_first="true">
		<support_file_type>.csv,.txt</support_file_type>
		<desc>file upload format  , first line : column name , data list from second line
			Lot
			1607D0437.00
			C610R7830.00
		</desc>
	</file_upload_opt>
</criteria>
```

3. source data set  &  single select / multi-select 要新增預選機制 

* 可設定多個 , 先找到先贏 ; 沒找到也不會報錯 , 就不預選

