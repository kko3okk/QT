# example1 : use is\_support\_file\_upload

```markup
<criteria id="c_date_option.keyin_glass_list" view_type="key_in" is_required="true" is_support_file_upload="true" label="Glass List" result_args="glass_list" next_criteria="step_group_list">
        <keyin_opt row="10" width="300">
                <desc>please key in glass id list , separated by ',' or change line.... </desc>
        </keyin_opt>
        <criteria_sql>glass_id in (#glass_list#) </criteria_sql>
         <file_upload_opt  is_skip_first="true">
            <support_file_type>.csv,.txt</support_file_type>
            <desc>file upload format  , first line : column name , data list from second line 
                    glass_id
                    g001
                    g002
            </desc>
        </file_upload_opt>
</criteria>  
```

