# example : EEAS客製化串接URL教學

```xml
<query_page query_tool_version="QT2" pre_criteria_version="QT2.1" is_support_analysis_preference="false" forward_url="/eeas-rest/profile_trend/draw.do">
	<criteria_list>
		<criteria id="date_option" view_type="radio" is_required="true" label="Selection Type" next_criteria="#radio_result#" >
			<radio_opt>
				<radio_item value="past_hour_01"         display_name="Past Hours" default_check="true"></radio_item>
				<radio_item value="date_range_01"        display_name="Date Range"></radio_item>
				<radio_item value="comp_id_list"        display_name="External Input"></radio_item>
			</radio_opt>
		</criteria>
		
		<criteria id="comp_id_list" view_type="key_in" is_required="true" is_support_file_upload="true" label="COMP ID" pre_criteria="date_option=comp_id_list" next_criteria="equip_type_list">
			<keyin_opt row="10" width="300">
				<desc>please key in comp id list , separated by ',' or change line.... </desc>
			</keyin_opt>						
			<file_upload_opt  is_skip_first="true">
				<support_file_type>.csv,.txt</support_file_type>
				<desc>file upload format  , first line : column name , data list from second line
				</desc>
			</file_upload_opt>
		</criteria>
```

{% hint style="info" %}
主要就是forward\_url : 定義QT按GO之後, 想到導向的頁面為何
{% endhint %}
