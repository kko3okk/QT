# next\_action

```markup
<criteria id="param_id_list" view_type="select" is_required="false" label="PARAM_ID" pre_criteria="step_id_list" result_args="param_id_list">
    <select_opt view_type="multiple" avail_from="avail_data_method" avail_data_method="get_avail_class3_list" />
    
    <next_action type="" name=""></next_action >
</criteria>
```

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| type | V | class / method |  |
| name | V |  |  |
| result\_arg |  |  | type="fuction"時才需要被定義 |

* type="method"
  * action\_code="get\_avail\_data"
  * 取得值之後, 回填到指定的result\_arg
* type="class"
  * action\_code="nextAction"



