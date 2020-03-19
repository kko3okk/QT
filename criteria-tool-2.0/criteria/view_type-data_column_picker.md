# view\_type="data\_column\_picker"

```markup
<criteria id="data_column"  view_type="data_column_picker" is_required="false" label="選擇欄位" group="1"/>          
```

* **NG 呼叫後端 :** 
  * **當遇到view\_type="data\_column\_picker" 的時候   固定呼叫 action\_code = get\_avail\_data\_column\_list  取得avail\_data\_column\_list**

{% hint style="danger" %}
**其他注意事項 : avail\_data\_column\_list 會回傳 XML 的欄位定義區塊的  column\_mapping &gt; column &gt; src\_col\_name  當作selected , display\_name 當作 ui display 回傳**
{% endhint %}

