# example3 : is\_support\_source\_data\_set

{% hint style="info" %}
確認QT2.0是否有修正此問題
{% endhint %}

使用此功能時 , **一定**要有一個Data\_Level\(criteria\_group\) 配上KeyIn , 決定要用什麼什麼來串sourceData

```markup
<criteria id="id_key" view_type="criteria_group" sel_type="radio" is_required="false" label="Key In ID" 
				result_args="id_key" next_criteria="#radio_result#" >
	<sub_criteria_list>
		<sub_criteria key="sbt_id_list"         radio_display_name="Strip ID"/>
		<sub_criteria key="d2id_list"       	radio_display_name="2D ID"/>
		<sub_criteria key="fuseid_list"       	radio_display_name="FUSE ID"/>
	</sub_criteria_list>
</criteria>

<criteria id="d2id_list" view_type="key_in" is_required="false" is_support_file_upload="true" label="2D ID List" result_args="d2id_list" next_criteria="step_id_list">
	<keyin_opt row="10" width="300" is_support_source_data_set="true">
		<desc>please key in 2D id list , separated by ',' or change line.... </desc>
	</keyin_opt>						
		<file_upload_opt  is_skip_first="true">
			<support_file_type>.csv,.txt</support_file_type>
			<desc>file upload format  , first line : column name , data list from second line
				2D ID
				3JR34QZ2	
				3JR39F6C	
			</desc>
		</file_upload_opt>
</criteria>
```

注意 , 有使用**is\_support\_source\_data\_set** , 必須在 **global\_args\_define** 加入以下三個變數 \(否則會報錯\) **:**

**\[**criteria-id**\].**source\_data\_set\_id

**\[**criteria-id**\].**column\_name

**\[**criteria-id**\].**distinct\_data\_list

```markup
<global_args_define>
		<arg name="d2id_list.source_data_set_id" from_id="source_data_set_distinct_data"          data_type="string" />
    <arg name="d2id_list.column_name" from_id="source_data_set_distinct_data"                 data_type="string"  />
    <arg name="d2id_list.distinct_data_list" from_id="source_data_set_distinct_data"          data_type="string_array"  />
</global_args_define>
```

