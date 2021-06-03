# db\_connection\_config

```markup
<db_connection_config>
    <connection id="saturn" type="from_tyne_plugin_db_t"  plugin_db_id="1"  />
    <connection id="SPARK" type="from_tyne_plugin_db_t"  plugin_db_id="4"  />            
</db_connection_config>
```

### connection

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| id |  |  |  |
| type |  | from\_tyne\_plugin\_db\_t /  | DB table :  tyne\_plugin\_db\_t |
| plugin\_db\_id |  | number / from\_ap | from\_ap : 使用AP的Logon connection做事情 |

{% hint style="info" %}
前景提要:  concurrent 客戶的連線數會被限制

若連線方式採用from\_ap的話,會使用與登入者相同的連線做事情,所以不會占用連線數

若連線方式採用撈plugin\__db\_t資訊的話,就會額外開新的連線,若帳號使用的是dbapp account,就會占用到客戶的連線數。_

所以當Qt在建立額外連線時不可以使用dbapp account,要使用 sys account。
{% endhint %}



