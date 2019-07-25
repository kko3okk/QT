# Date Option

```markup
<criteria id="c_date_option.past_day" view_type="date" is_required="true" label="Past Days" 
			result_args="past_days,past_days_start_hh,past_days_start_mm"  next_criteria="step_id_list" >
	<date_opt date_type="past_days" default_value="1" />
	<past_days_opt start_time="00:00"  />			
</criteria>
```

### date\_opt

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| date\_type | V | past\_days / date\_range / past\_hours / date\_range\_DTN/date\_range\_WTD/ date\_range\_MTD | 判斷 user 所選的 date\_type為何 |
| default\_value |  |  |  |
| start\_time |  |  |  |
| end\_time |  |  |  |
| start\_date |  |  | DTN start\_date 一定是 today ;          WTD  start\_date  : monday \|\| tuesday \|\| wednesday;                                            MTD  start\_date : 1\_of\_month  \|\| 2\_of\_month ...... |
| start\_hhmm |  |  |  |
| end\_date |  |  | DTN end\_date一定是today |
| end\_hhmm |  |  |  |
| max\_count |  |  | 選取天數的最大值 \(單位 : 天\) |
| date\_column\_name\_list |  |  | 需要處理的欄位 |
| date\_src\_mode |  |  | 處理日期模式 |

### past\_days\_opt 

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| start\_time |  |  |  |
| end\_time |  |  |  |

