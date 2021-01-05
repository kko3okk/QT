# query\_sql

```markup
<query_sql use_connection_id="SPARK" mode="plugin_class" class_name="com.tynesys.chot.qt.QTSqlHandler">
    <sql>
    select glass_id ,step_id, glass_start_time, product_id, equip_id , item1 as lot_id 
    from array_glass_t, array_step_t 
    where array_step_t.step_id = array_glass_t.step_id #criteria_replace_sql# order by glass_start_time
    </sql>
    <column_mapping>
        <column src_col_name="array_glass_t.glass_id" data_type="VARCHAR2" display_name="glass_id"  />
        <column src_col_name="array_glass_t.step_id" data_type="VARCHAR2" display_name="step_id"  />
        <column src_col_name="array_glass_t.glass_start_time" data_type="DATE" display_name="glass_start_time"  />            
        <column src_col_name="array_glass_t.product_id" data_type="VARCHAR2" display_name="product_id"  />
        <column src_col_name="array_glass_t.equip_id" data_type="VARCHAR2" display_name="equip_id"  />
        <column src_col_name="array_glass_t.item1" data_type="VARCHAR2" display_name="lot_id"  />  
    </column_mapping>
</query_sql>
```

### query\_sql

<table>
  <thead>
    <tr>
      <th style="text-align:left">Attributes</th>
      <th style="text-align:left">Required</th>
      <th style="text-align:left">Parameters</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">use_connection_id</td>
      <td style="text-align:left">V</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">mode</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">plugin_class/</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">class_name</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">plugin_opt</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">build_sql_and_create_view</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">process_result</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">true/false</td>
      <td style="text-align:left">&#x555F;&#x52D5;Innotron&#x8F49;&#x7F6E;&#x529F;&#x80FD;</td>
    </tr>
    <tr>
      <td style="text-align:left">process_result_opt</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>DS_DATA_PATH_SEL.DATA_PATH_METROLOGY</p>
        <p>_WAFER_SUMMARY_V@@LOT</p>
      </td>
      <td style="text-align:left">&#x50B3;&#x905E;&#x53C3;&#x6578;</td>
    </tr>
  </tbody>
</table>

#### sql

編輯點GO之後做的動作

#### column\_mapping

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| mode |  | eda\_lookup/  |  |
| is\_need\_pre\_process\_arg\_map |  |  |  |

#### **eda\_lookup\_opt**

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| lookup\_mode |  | datapath**/**table\_list |  |
| datapath |  |  |  |
| table\_list |  |  |  |

#### column

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| src\_col\_name | V |  |  |
| data\_type | V | VARCHAR2/ DATE/ NUMBER |  |
| display\_name | V |  |  |

{% hint style="info" %}
在oracle mode的時候, 經常超過where condition in 數量 &gt; 1000 , 

會發生錯誤 所以在2021/01/05在prod code加上判斷: 

1.mode = 'oracle' 且value list count &gt; 1000 時, 就是將值塞到ds\_value\_list\_s

2.ds\_value\_list\_s- key = criteria arg\_name
{% endhint %}

{% hint style="info" %}
fetch data 走prod code\(非plugin\_class\) , 規則同上
{% endhint %}

