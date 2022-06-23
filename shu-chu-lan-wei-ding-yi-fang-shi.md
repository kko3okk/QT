# 輸出欄位定義方式

```markup
<query_sql use_connection_id="saturn" >
     <sql>
     from array_pds_glass_t ,array_pds_glass_summary_t  where 1=1  #criteria_replace_sql# and array_glass_t.step_id= array_step_t.step_id   order by array_pds_glass_t.glass_start_time
     </sql>
     <column_mapping mode="eda_lookup"  is_need_pre_process_arg_map=”true”>   	    
    	     <eda_lookup_opt  lookup_mode=”datapath” datapath="DS_ARRAY_DATA_PATH_SEL.DATA_PATH_ARRAY_DEFECT_T"   step_id_list_arg="step_id_list"   />
     </column_mapping mode="eda_lookup"  >
</query_sql>
```

### 模式一  : SQL 內直接指定

* 直接在query\_sql -> sql 內寫select array\_glass\_t.glass\_id , array\_glass\_t.step\_id …

### 模式二 : XML 內定義展開的column\_mapping

* 透過column\_mapping目前無法按照XML定義的順序呈現 , 需要配合lookup table來決定顯示順序
  * 有定義在column\_mapping的就會到lookup table取得順序

```markup
<column_mapping>
    <column src_col_name="array_glass_t.glass_id" data_type="VARCHAR2" display_name="glass_id"   item_flag=”glass_id” />
    <column src_col_name="array_glass_t.step_id" data_type="VARCHAR2" display_name="step_id" item_flag =”step_id”  />
 </column_mapping>
```

### 模式三 : 走lookup  column\_mapping/mode : optional

* **mode = "eda\_lookup" , 走lookup table 方式取得欄位清單**

**datapath**

```markup
<column_mapping mode="eda_lookup"  >           
    <eda_lookup_opt lookup_mode=”datapath” datapath="DS_ARRAY_DATA_PATH_SEL.DATA_PATH_ARRAY_DEFECT_T"   step_id_list_arg="step_id_list"   />
</column_mapping>
```

**table\_list**

```markup
<column_mapping mode="eda_lookup"  >           
      <eda_lookup_opt lookup_mode=”table_list” table_list="array_glass_t,array_defect_t" step_id_list_arg="step_id_list"   />
</column_mapping>
```

{% hint style="info" %}
走eda\_lookup 的時候, 會依據step\_id\_list\_arg 的變數內容當作 選定的step\_id , 往後拉取item 的時候, 用那些step id 去以下table 過去by step 定義的欄位

&#x20;select \* from ds\_lookup\_step\_item\_t where table\_name = 'ARRAY\_DEFECT\_T' AND STEP\_ID = 'T8920'

**ex : 我的範例当选到T8920 的时候才会出现以上sql 出来的栏位**
{% endhint %}

* **mode = "plugin\_class" , 透過plugin\_class的方式來取得**

1. 此模式直接使用QT 的plugin class , 新增一組public ArrayList genColumnMapping,來讓QT product code 來呼叫plugin class 取得該欄位清單

{% hint style="info" %}
此種模式可以取得當UI的所有argMap , 讓plugin class 可以取得所有已經設定的UI 條件做邏輯判斷&#x20;

EX : V3 會在上面指定UI 上先選EQP\_TYPE , 才會走到欄位清單, 因此v3 可以用EQP\_TYPE 以及xml 內定義的table\_list 來決定欄位清單有哪些
{% endhint %}

### column\_mapping : 設定取得column\_mapping 需要進行前處理 argMap

1. 若是走eda\_lookup 並且需要處理到item51 , 那取得lookup 時必須先指定 step\_id\_list , 特殊情況下step\_id\_list 無法直接從UI 選完的ArgMap 中取得 (ex : CSOT 虛擬站點)
2. 因此提供以下plugin class method 若有定義is\_need\_pre\_process\_arg\_map=”true” , 則QT 在取得column mapping 程式運作前, 會先呼叫以下method 由plugin class 自行看怎樣調整ArgMap , 並回傳給QT
3. CSOT 案例用法是 指定step\_id\_list\_for\_lookup Arg , 而這Arg 是透過 preProcessArgMap 處理後新增至ArgMap 內

{% hint style="info" %}
**小技巧  , 從ds\_lookup\_item\_t 轉出來**
{% endhint %}

```sql
select '<column src_col_name="' || TABLE_NAME || '.' || ITEM_NAME ||
       '" data_type="VARCHAR2" display_name="' || DISPLAY_NAME || '" />'
  from ds_lookup_item_t
 where table_name = 'ARRAY_GLASS_HST_T'
 ORDER BY DISPLAY_SEQ
```

### 可選取要顯示的欄位清單

* XML 訂法 : 一定要照以下紅色的, 不能更改

```markup
global_args_define
<arg name="data_column_list"     from_id="data_column_list"                     data_type="string_array"  />

criteria_list
<criteria id="data_column_list"  view_type="data_column_picker" is_required="false" label="Column List" pre_criteria="equip_id_list" result_args="data_column_list"  >
</criteria>
```

#### NG 呼叫後端 :&#x20;

當遇到view\_type="data\_column\_picker" 的時候 固定呼叫 action\_code = get\_avail\_data\_column\_list 取得avail\_data\_column\_list 其他注意事項 : avail\_data\_column\_list 會回傳 XML 的欄位定義區塊的 column\_mapping > column > src\_col\_name 當作selected , display\_name 當作 ui display 回傳
