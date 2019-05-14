# PlugIn class

* mode="plugin\_class" , 定義 class\_name="com.tynesys.pti.qt.QTSqlHandler" 
* 該Class裡面 , 必須要有Function = **buildSql ,** 且參數必須遵守以下範例 :

```java
public String buildSql(HttpSession session, String analysisId, DataSourceDefine dataSourceDefine,
	Connection sparkConn, String after_replace_query_sql_str, HashSet<String> selectedCriteriaIdSet,
	Hashtable<String, ArgInfo> argMap){
	
	.........................
	
}
```



