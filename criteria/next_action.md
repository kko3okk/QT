# next\_action

```markup
<criteria id="param_id_list" view_type="select" is_required="false" label="PARAM_ID" pre_criteria="step_id_list" result_args="param_id_list">
    <select_opt view_type="multiple" avail_from="avail_data_method" avail_data_method="get_avail_class3_list" />
    
    <next_action type="" name="" action_code=""></next_action >
</criteria>
```

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| mode | V | plugin\_class / method | method先不實做 |
| name | V |  | ex : com.tynesys.edatool.struts.query\_tool.plugin.CsotQtBuilder |
| action\_code |  |  | ex : PROCESS\_STPE\_ID |

### 流程

* 有定義**next\_action**時 , 會觸發class\_path裡面的 function - **processArgMap**
  * 注意觸發順序 : next\_action 要在 next\_criteria 之前
  * 假如有更新舊有的Arg , 需要注意是否UI會同步更新
  * 選值的過程中 ,  需要注意是否都有呼叫到 next\_action  \(會影響ArgMap的正確性\) 
* 回傳值為ArrayList , 已有值做更新 , 不存在就新增 \(用name來判斷\)
* 前端呼叫後端的action\_code = "nextAction" : 需傳遞參數 - criteria\_id

