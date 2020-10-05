# view\_type="data\_column\_picker"

```markup
<criteria id="data_column"  view_type="data_column_picker" is_required="false" label="選擇欄位" group="1"/>          
```

* **NG 呼叫後端 :** 
  * **當遇到view\_type="data\_column\_picker" 的時候   固定呼叫 action\_code = get\_avail\_data\_column\_list  取得avail\_data\_column\_list**

{% hint style="danger" %}
**其他注意事項 : avail\_data\_column\_list 會回傳 XML 的欄位定義區塊的  column\_mapping &gt; column &gt; src\_col\_name  當作selected , display\_name 當作 ui display 回傳**
{% endhint %}

```markup
<criteria id="data_column"  view_type="data_column_picker" is_required="false" label="選擇欄位" group="1" column_from_self="true">  
      <column_mapping>
            <column src_col_name="array_glass_t.glass_id" data_type="VARCHAR2" display_name="GLASS_ID"  />
            <column src_col_name="array_glass_t.step_id" data_type="VARCHAR2" display_name="STEP_ID"  />
            <column src_col_name="array_glass_t.glass_start_time" data_type="DATE" display_name="GLASS_START_TIME"  />            
            <column src_col_name="array_glass_t.product_id" data_type="VARCHAR2" display_name="PRODUCT_ID"  />
            <column src_col_name="array_glass_t.equip_id" data_type="VARCHAR2" display_name="EQUIP_ID"  />
            <column src_col_name="array_glass_t.item1" data_type="VARCHAR2" display_name="LOT_ID"  />  
			      <column src_col_name="array_defect_t.item1" data_type="VARCHAR2" display_name="DEFECT_ID"  /> 
      </column_mapping>  
</criteria>      
```

{% hint style="info" %}
一樣呼叫get\_avail\_data\_column\_list , 多傳criteria\_id , 以利判斷來自於哪個物件
{% endhint %}

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| column\_from\_self |  | true /false  | 預設值=false |

### column\_mapping

* 欄位輸出方式請參考 :  [輸出欄位定義方式](../../shu-chu-lan-wei-ding-yi-fang-shi.md)

