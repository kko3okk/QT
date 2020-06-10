# 開發進度規劃

## QT2.1

針對目前較急的需求 , 先行作業

<table>
  <thead>
    <tr>
      <th style="text-align:left">Finish Date</th>
      <th style="text-align:left">Item</th>
      <th style="text-align:left">Desc</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">6/8(done)</td>
      <td style="text-align:left">QT &#x76F8;&#x95DC;&#x898F;&#x7BC4;&#x516C;&#x5E03;</td>
      <td style="text-align:left">
        <ol>
          <li>QT owner &#x6E2C;&#x8A66;&#x7BC4;&#x7587;</li>
          <li>SVN &#x653E;&#x7F6E;&#x898F;&#x5B9A;</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>6/12(6/10-</p>
        <p>done)</p>
      </td>
      <td style="text-align:left">QT &#x7E7C;&#x627F;&#x6A5F;&#x5236;</td>
      <td style="text-align:left">
        <p></p>
        <ol>
          <li>&#x53EF;&#x4EE5;by criteria id &#x6574;&#x7D44;&#x62FF;base &#x7684; ,
            &#x7528; replace_by_base=&quot;true&quot;</li>
          <li>avail_data_method_list &#x5167; , &#x53EF;&#x4EE5;&#x5403;arg map &#x7684;&#x8B8A;&#x6578;avail_data_method_list
            =&gt; &#x653E;base (&#x7236;) ; arg map &#x653E;&#x4E0A;&#x5C64;(&#x5152;&#x5B50;)</li>
          <li>db_connection_config &#x5B9A;replace_by_base</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">TBD</td>
      <td style="text-align:left">pre_criteria &#x908F;&#x8F2F;&#x65B0;&#x589E;</td>
      <td style="text-align:left">
        <p>pre_criteria_logic= &quot;and&quot;</p>
        <p>pre_criteria=&quot;normal.product_id,condition_type=seleted_by_preprocess&quot;</p>
        <p>* pre_criteria &#x5148;&#x7528;&quot;,&quot; &#x5206;&#x9694; , &#x62C6;&#x51FA;&#x591A;&#x500B;&#x5F8C;
          ,</p>
        <p>&#x6BCF;&#x4E00;&#x500B;&#x82E5; &#x7121;&#x7B49;&#x865F; ==&gt; &#x73FE;&#x6CC1;
          (&#x53EA;&#x770B;&#x8A72;criteria id &#x6709;&#x8A2D;&#x5B9A; &#x5C31;pass</p>
        <p>&#x6BCF;&#x4E00;&#x500B;&#x82E5; &#x6709;&#x7B49;&#x865F; ==&gt; criteria
          id &#x6709;&#x8A2D;&#x5B9A; &#x4E14;&#x7B26;&#x5408; = &#x5F8C;&#x9762;&#x7684;value
          &#x624D;pass</p>
      </td>
    </tr>
  </tbody>
</table>

## QT2.2

針對可優化功能 , 做改善

| Finish Date | Item | Desc |
| :--- | :--- | :--- |
| TBD | Load XML to memory vs Load File |  |
| TBD | 目前使用QT全部XML都會被讀取一次 , 希望改成用哪一隻讀哪一隻XML |  |
| TBD | 日期格式的處理 |  |

## QT2.3

異動較大 , 需花較多時間 ; 但不影響現況

| Finish Date | Item | Desc |
| :--- | :--- | :--- |
| TBD | 從Serverlet 改成 Restful |  |
| TBD | QT - Ant流程修改安排  | 將QT的code , 包版後能夠自動包進去 |

## 其餘需求

針對專案需求 , 再安排進度

| Finish Date | Item | Desc |
| :--- | :--- | :--- |
| TBD | 支援i18n |  |

