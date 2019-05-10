# Key In

```markup
<criteria id="sbt_id_list" view_type="key_in" is_required="false" is_support_file_upload="true" label="SBT ID List" result_args="sbt_id_list" next_criteria="step_id_list">
	<keyin_opt row="10" width="300">
		<desc>please key in SBT id list , separated by ',' or change line.... </desc>
	</keyin_opt>						
	<file_upload_opt  is_skip_first="true">
		<support_file_type>.csv,.txt</support_file_type>
		<desc>file upload format  , first line : column name , data list from second line
			sbt_id
			AALDA-190128	
			AALDA-190129	
		</desc>
	</file_upload_opt>
</criteria>
```

### keyin\_opt

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| row | V |  |  |
| width | V |  |  |
| is\_support\_file\_upload |  | true / false |  |
| is\_support\_im |  | true / false |  |
| is\_support\_source\_data\_set |  | true / false |  |

### file\_upload\_opt

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| is\_skip\_first |  | true / false |  |

### support\_file\_type

規定可被上傳檔案的副檔名

### desc

UI上顯示的描述

