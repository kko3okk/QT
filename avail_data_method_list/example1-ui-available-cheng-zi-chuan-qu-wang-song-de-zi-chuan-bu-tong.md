---
description: '以下是選取到時要記住equip_id , 而顯示在UI 時要顯示 equip(equip_group)'
---

# example1 : UI 選項available 呈現字串與選取後, 往後送的字串不同

```markup
<avail_data_method id="get_avail_equip_id_list"  args="equip_group_list" >
    <query_sql use_connection_id="edadbt" >select distinct equip_id , equip_id||'(' ||equip_group ||')' from array_equip_t where equip_group in (#equip_group_list#)  and equip_id like '%00' order by equip_id</query_sql>
</avail_data_method>
```



```markup
distinct equip_id , equip_id||'(' ||equip_group ||')'
```

![UI &#x5448;&#x73FE;&#x756B;&#x9762;](../.gitbook/assets/image-1%20%281%29.png)

