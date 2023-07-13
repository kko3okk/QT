# view\_type="key\_in"

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

## criteria

| Attributes        | Required | Parameters | Description                                                                   |
| ----------------- | -------- | ---------- | ----------------------------------------------------------------------------- |
| replace\_separate |          |            | ex : replace\_separate = "@" 前端會將逗號替換後 , 放入arg\_map , 從preference載入時 , 再將@替換成 |

### keyin\_opt

| Attributes                     | Required | Parameters    | Description                                                                       |   |   |
| ------------------------------ | -------- | ------------- | --------------------------------------------------------------------------------- | - | - |
| row                            | V        |               |                                                                                   |   |   |
| width                          | V        |               |                                                                                   |   |   |
| is\_support\_file\_upload      |          | true / false  |                                                                                   |   |   |
| is\_support\_im                |          | true / false  |                                                                                   |   |   |
| is\_support\_source\_data\_set |          | true / false  |                                                                                   |   |   |
| max\_count                     |          |               | UI最大輸入的數量 , 超過顯示錯誤訊息 : ERR\_MSG> remains is over \[設定值] . Please reduce the list. |   |   |
| view\_type                     |          | key\_in/input |                                                                                   |   |   |
| default\_value                 |          |               | 預選值                                                                               |   |   |
| show\_button                   |          | true / false  | 預設=true;當設定false時，UI就不會做set\_value、next\_criteria，單純只存設定值在arg內.                   |   |   |
|                                |          |               |                                                                                   |   |   |

### file\_upload\_opt

| Attributes      | Required | Parameters   | Description |
| --------------- | -------- | ------------ | ----------- |
| is\_skip\_first |          | true / false |             |

### source\_data\_set\_opt

| Attributes  | Required | Parameters | Description |
| ----------- | -------- | ---------- | ----------- |
| pre\_select |          |            | 預選值         |

### support\_file\_type

規定可被上傳檔案的副檔名

### desc

UI上顯示的描述
