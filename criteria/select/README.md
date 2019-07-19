# Select

```markup
<criteria id="param_id_list" view_type="select" is_required="false" label="PARAM_ID" pre_criteria="step_id_list" result_args="param_id_list">
    <select_opt view_type="multiple" avail_from="avail_data_method" avail_data_method="get_avail_class3_list" />
</criteria>
```

### select\_opt

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| view\_type |  | single / multiple |  |
| avail\_from |  | constants / avail\_data\_method |  |
| avail\_data\_method |  |  | 填入 取得 avail data 的 method ID, method id 會對應到&lt;avail\_data\_method\_list&gt; 的&lt;avail\_data\_method&gt; 的 ID |
| is\_support\_im |  |  |  |
| pre\_select |  |  | 預選值 |
| max\_count |  |  | 選取參數的最大值 |
| default\_select\_when\_one\_available  |  | true / false | 預選該唯一的available |
| default\_select\_and\_hide\_when\_one\_available |  | true / false | 預選且該criteria 隱藏 |

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

