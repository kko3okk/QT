# example1 : retest / rework 重工重檢

```markup
<criteria id="c_is_include_retest"  view_type="checkbox" is_required="false" label="重工/重测"  result_args="is_include_old_data">
    <checkbox_opt check_type="single">
        <check_item value="TRUE"  display_name="include rework/retest" default_check="true" />
    </checkbox_opt>
    <criteria_sql mode="logic">
        <when_null arg="is_include_old_data" >
                <sql>array_glass_t.ITEM7 ='V'</sql>
        </when_null>
        <equals   arg="is_include_old_data" value="TRUE">
        </equals>    
     </criteria_sql>
</criteria>

```

