# Stpe4 : 新增至EDA中

* 將QT XML放到 \[catalina\_home\]/webapps/\[app\_name\]/Server\_File/QT
* 執行以下SQL

```sql
insert into tyne_analysis_t values ('SMS_SUMMARY','SMS_SUMMARY','SMS_SUMMARY','Production',null);
insert into tyne_menu_t (analysis_id, parent_menu_index, display_seq,  web_ui_cmd,menu_name )
    select 'SMS_SUMMARY',
           to_number((select menu_index from tyne_menu_t where  parent_menu_index = 0 and menu_name = 'Production')) ver,
           12,
            '/edatool/query_tool/ds_main.do?analysis_id=SMS_SUMMARY&query_ds_id=SMS_SUMMARY',
           'SMS_SUMMARY'    from dual;

insert into edatool_query_tool_plugin_t (QUERY_TOOL_ID, DISPLAY_NAME, CRITERIA_XML, UPDATE_TIME, DISPLAY_SEQ, PLUGIN_DB_ID, QUERY_TOOL_TYPE)
values ('SMS_SUMMARY', 'SMS_SUMMARY', null, sysdate, 1, '1', 'DS_FUNCTION');
```



