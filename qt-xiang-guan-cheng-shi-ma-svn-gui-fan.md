# QT 相關程式碼 - SVN規範

開發QT時 , 有3個地方需要同步到SVN上 

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x9805;&#x76EE;</th>
      <th style="text-align:left">&#x8AAA;&#x660E; (&#x4EE5;&#x4E0B;&#x7BC4;&#x4F8B;&#x5BA2;&#x6236;&#x5225;&#x4EE5;LEDA_CSOTT7&#x70BA;&#x4F8B;)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">QT XML</td>
      <td style="text-align:left">
        <ol>
          <li>&#x8ACB;&#x540C;&#x6B65;&#x5230;&#x5BA2;&#x6236;&#x5225;&#x7684;&#x76EE;&#x9304;&#x4E0B;
            (ex : LEDA_CSOTT7/QT/XML)</li>
          <li>&#x76EE;&#x524D;&#x4E00;&#x5F8B;&#x898F;&#x5B9A;XML&#x653E;&#x7F6E;&#x8DEF;&#x5F91;&#x70BA;
            ex : AYDA_CSOTT7_TEST/Server_File/QT</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">QT plugin_class</td>
      <td style="text-align:left">
        <p></p>
        <ol>
          <li>&#x8ACB;&#x540C;&#x6B65;&#x5230;&#x5BA2;&#x6236;&#x5225;&#x7684;&#x76EE;&#x9304;&#x4E0B;
            (ex : LEDA_CSOTT7/QT/plugin_class)</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">QT config &#x76F8;&#x95DC;SQL</td>
      <td style="text-align:left">
        <ol>
          <li>&#x540C;&#x6B65;&#x5230;LEDA_CSOTT7/db/data &#x5404;&#x500B;load file&#x4E2D;</li>
        </ol>
      </td>
    </tr>
  </tbody>
</table>Ant 流程 :

1. 只要檢查到客戶別下有QT目錄夾 , 就會另外tyne\release 下多一包QT的目錄夾
2. 其中內容要包含 : QT/XML ,  QT/plugin\_class
3. 其中要注意的是 QT/plugin\_class : 內容要包含java source &  java class
   1. QT/plugin\_class/source\_code : java source
   2. QT/plugin\_class/compiler\_code : java class

上板流程 :

1. AP按照SOP做完所有動作後 , 從QT/XML 拿到最新的 XML , 更新到 Server\_File/QT
2. 將 QT/plugin\_class/compiler\_code 放到 WEB-INF/classes
3. QT/plugin\_class/source\_code 根據開發需求 , 判斷是否要同步到客戶家開發環境

