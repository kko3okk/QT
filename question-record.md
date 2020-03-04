# Troubleshooting

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

{% hint style="info" %}
因為Spark的關係 , 撈資料都是在同一座Spark create view 之後撈資料 ; 所以是合理的
{% endhint %}

## 假如呼叫不到QueryToolService , 要如何解決 ?

{% hint style="info" %}
請檢查Web.xml裡面是否有這一段 ; 沒有的話請加上, 並且重啟Tomcat
{% endhint %}

```markup
<servlet>
	<servlet-name>queryToolService</servlet-name>
	<servlet-class>com.tynesys.edatool.struts.query_tool.servlet.QueryToolService</servlet-class>
</servlet>

<servlet-mapping>
	<servlet-name>queryToolService</servlet-name>
	<url-pattern>/queryToolService/*</url-pattern>
</servlet-mapping>
```

## 外部 link to EDA - QT , 查出來的結果不是我從 URL 帶進去的兩個 glass\_id ?

{% hint style="info" %}
請確認是否有達到2個前提

1.Load10 config: QT.DRILL\_DOWN\_DATA\_MAPPING\_CLASS\_NAME, 設定外部 Driil Down 的資訊替換成 DS Query Tool 可執行的相關程式路徑

2.該路徑下是否有放替換的程式 \(function名稱請參考以下\)
{% endhint %}

```java
package com.tynesys.drilldown;

import com.tynesys.edatool.struts.query_tool.bean.CriteriaDataMap;
import com.tynesys.framework.logon.LCDDrillDown;

public class drillDownSample {
	
	public CriteriaDataMap replaceValue(LCDDrillDown drillDownObj, CriteriaDataMap o_criteriaDataMap){
		
		String value = drillDownObj.get("COMPONENT_ID_LIST");
		
		o_criteriaDataMap.getArgInfo("glass_list").setData_Value(value);
		
		return o_criteriaDataMap;
	}

}
```

