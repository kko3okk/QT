# view\_type="select"

```markup
<criteria id="param_id_list" view_type="select" is_required="false" label="PARAM_ID" pre_criteria="step_id_list" result_args="param_id_list">
    <select_opt view_type="multiple" avail_from="avail_data_method" avail_data_method="get_avail_class3_list" />
</criteria>
```

### select\_opt

| Attributes                                       | Required | Parameters                                               | Description                                                                                                  |
| ------------------------------------------------ | -------- | -------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| view\_type                                       |          | single / multiple                                        |                                                                                                              |
| avail\_from                                      |          | <p>constants / avail_data_method/</p><p>plugin_class</p> |                                                                                                              |
| avail\_data\_method                              |          |                                                          | 填入 取得 avail data 的 method ID, method id 會對應到\<avail\_data\_method\_list> 的\<avail\_data\_method> 的 ID        |
| data\_method\_arg                                |          |                                                          | ex : data\_method\_arg="tab\_shop=array" 替換method裡面SQL , 用##包住的變數 (順序 : data\_method\_arg -> 一般argmap)       |
| is\_support\_im                                  |          |                                                          |                                                                                                              |
| is\_support\_all\_flag                           |          | true/false                                               | 是否顯示ALL Button                                                                                               |
| is\_support\_wildcard                            |          | true/false                                               | 顯示文字輸入框，允許輸入wildcard搜尋字串                                                                                     |
| all\_flag\_var                                   |          | ex : param\_name\_list\_all                              | 存放all flag是否開啟的參數                                                                                            |
| pre\_select                                      |          |                                                          | 預選值                                                                                                          |
| max\_count                                       |          |                                                          | 若用戶針對select 元件, 選擇內容個數操作max\_selected\_count 時, 前端直接拋出 ""\[criteria name] 選擇個數超過限制 (\[max\_selected\_count]) |
| default\_select\_when\_one\_available            |          | true / false                                             | 預選該唯一的available                                                                                              |
| default\_select\_and\_hide\_when\_one\_available |          | true / false                                             | 預選且該criteria 隱藏                                                                                              |
| is\_support\_clear                               |          | true / false                                             | 是否顯示Clear Button                                                                                             |

{% hint style="info" %}
default\_select\_when\_one\_available / default\_select\_and\_hide\_when\_one\_available : **不能同時設定 , 只能設定一種**
{% endhint %}

### avail\_constants

定義有哪些固定的Variable ,  ex :

```markup
<criteria id="step_id_list"  view_type="select" is_required="false" label="Step ID"  result_args="step_id_list" 
		 avail_data_method.args="equip_group_list">
	<select_opt view_type="multiple" avail_from="constants" />
	<avail_constants>A41,A421,A501,A412S2,A424,A413S2,A413,A415,A71,A53,A710,A425,A111,A422,A119,A411S1,A411,A50,A417,A42,A701,A416,A66,A423,A414,A411S2,A414S2,A412,A51,A412S1,A413S4</avail_constants>
</criteria>
```
