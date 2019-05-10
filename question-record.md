# Question Record

## 系統mode = spark時, db\_connection\_config 的設定沒用  ?

根據程式碼來看 , 只要是spark就會拿session的連線 , 是否合理 ?

```java
if (isSparkMode) {
	connFromPulgin = false;
	conn = WebGlobal.getConnection(session);
	debugUtil.logDebugStr(analysisId, "QUERY_TOOL_FETCH_DATA_CONN_TYPE",
			"SparkMode-set-from-properties", "");
} else {
	ConnDefine dbConnection = dataSourceDefine.getDBConnection(fetchDataConnId);
	if (dbConnection != null && dbConnection.getType().equals("from_tyne_plugin_db_t")) {
		String dbId = dbConnection.getPlugin_db_id();
		conn = getPluginConnection(session, dbId);
	}
	String logMessage = (conn == null) ? "Error: xml missing connection Type!"
			: "SparkMode-set-from-xml";
	debugUtil.logDebugStr(analysisId, "QUERY_TOOL_FETCH_DATA_CONN_TYPE", logMessage, "");
}
```

## 後續需要開放select 欄位到 pluginclass 裡面 , 

