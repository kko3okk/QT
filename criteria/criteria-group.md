# Criteria Group

```markup
<criteria id="c_date_opt" view_type="criteria_group" sel_type="radio" is_required="true" label="Date Option" 
				result_args="date_option" next_criteria="#radio_result#" >
	<sub_criteria_list>
		<sub_criteria key="c_date_option.past_day"  radio_display_name="Past Days"/>
		<sub_criteria key="c_date_option.date_range" radio_display_name="Date Range"/>
	</sub_criteria_list>
</criteria>
```

### sub\_criteria\_list

| Attributes | Required | Parameters | Description |
| :--- | :--- | :--- | :--- |
| key | V |  |  |
| radio\_display\_name | V |  |  |

```text
取得ID : [criteria_id]+'.'+ 'input_option'
```



