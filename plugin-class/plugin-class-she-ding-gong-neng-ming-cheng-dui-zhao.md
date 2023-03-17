# Plugin class 設定 - 功能名稱對照



| Tag名稱                                                                                                                                   | 參數                                                               | 功能名稱                                               |
| --------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------- | -------------------------------------------------- |
| [query\_sql](../query\_sql/)                                                                                                            | mode="plugin\_class"                                             | buildSql                                           |
| [query\_sql](../query\_sql/)                                                                                                            | mode="plugin\_class\&plugin\_opt="build\_sql\_and\_create\_view" | buildSqlAndCreateView                              |
| [column\_mapping](../shu-chu-lan-wei-ding-yi-fang-shi.md#columnmapping-she-ding-qu-de-columnmapping-xu-yao-jin-hang-qian-chu-li-argmap) | mis\_need\_pre\_process\_arg\_map="true"                         | preProcessArgMap                                   |
| [next\_action](../criteria-tool-2.0/next\_action.md)                                                                                    | mode="plugin\_class"                                             | processArgMap                                      |
| [select](../criteria-tool-2.0/criteria/view\_type-select/)                                                                              | avail\_from="plugin\_class"                                      | pluginGetAvail                                     |
| [Query page](../criteria-tool-2.0/query-page/)                                                                                          | query\_by\_pluginclass="true"                                    | queryData                                          |
| [Query page](../criteria-tool-2.0/query-page/)                                                                                          | query\_by\_pluginclass="true"                                    | queryData\_ET                                      |
| [query\_sql](../query\_sql/)                                                                                                            | process\_result="true"                                           | processResult                                      |
| [column\_mapping](../shu-chu-lan-wei-ding-yi-fang-shi.md#mo-shi-san-zou-lookup-columnmappingmode-optional)                              | mode="plugin\_class"                                             | genColumnMapping                                   |
| [data\_column\_picker](../criteria-tool-2.0/criteria/view\_type-data\_column\_picker.md)                                                | mode not define                                                  | getColumnMapping                                   |
| [data\_column\_picker](../criteria-tool-2.0/criteria/view\_type-data\_column\_picker.md)                                                | ode="plugin\_class"                                              | get\_selected\_column\_display\_name\_list\_plugin |
| [Query page](../criteria-tool-2.0/query-page/)                                                                                          | query\_by\_pluginclass="true"                                    | checkSettingForSavePref                            |

{% hint style="info" %}
總表請參考: com.tynesys.edatool.struts.query\_tool.plugin.SqlBuilderImpl
{% endhint %}

{% hint style="info" %}
plugin\_class路徑都定義在query\_sql-class\_name
{% endhint %}
