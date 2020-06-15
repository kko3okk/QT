# Criteria

{% hint style="warning" %}
1. 需要Review 目前有哪些元件 ; 以及內容是否有作修改

2. ui\_group\_style 命名需要定義 \(Wen會提供class名稱\)

3.T7 DS 畫面 , 目前html是不同一份 \(需要再確認 \)  ; 顏色/展開 是否能用設定控制 \(OK\)
{% endhint %}

<table>
  <thead>
    <tr>
      <th style="text-align:left">Attributes</th>
      <th style="text-align:left">Required</th>
      <th style="text-align:left">Parameters</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">id</td>
      <td style="text-align:left">V</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">&#x91CD;&#x8981; !! &#x7B2C;&#x4E00;&#x7FA4;&#x64F7;&#x53D6;&#x65E5;&#x671F;&#x7684;radio
        group, &#x6C92;&#x6709;&#x4F7F;&#x7528;plugin_class&#x6642; , id&#x8ACB;&#x56FA;&#x5B9A;&#x53EB;
        : c_date_opt ; Prod code&#x8A8D;&#x5B57;&#x773C;&#x505A;&#x4E8B;&#x60C5;</td>
    </tr>
    <tr>
      <td style="text-align:left">view_type</td>
      <td style="text-align:left">V</td>
      <td style="text-align:left">ui_group</td>
      <td style="text-align:left">UI&#x4E0A;&#x5448;&#x73FE;&#x7684;&#x5206;&#x7FA4;</td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"><a href="view_type-checkbox.md">checkbox</a>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"><a href="view_type-radio.md">radio</a>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"><a href="view_type-date.md">date</a>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"><a href="view_type-key_in/">keyin</a>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">is_required</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left">&#x9810;&#x8A2D;&#x503C; = false</td>
    </tr>
    <tr>
      <td style="text-align:left">label</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left">&#x6C92;&#x8F38;&#x5165;&#x4EE3;&#x8868;&#x5143;&#x4EF6;&#x524D;&#x4E0D;&#x986F;&#x793A;Label</td>
    </tr>
    <tr>
      <td style="text-align:left">result_args</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left">&#x53EF;&#x4E0D;&#x5B9A;&#x7FA9; (&#x7CFB;&#x7D71;&#x81EA;&#x52D5;&#x7522;&#x751F;)</td>
    </tr>
    <tr>
      <td style="text-align:left">pre_criteria_logic</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">and/or</td>
      <td style="text-align:left">&#x9810;&#x8A2D;&#x503C;=and</td>
    </tr>
    <tr>
      <td style="text-align:left">pre_criteria</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>&#x8ACB;&#x53C3;&#x8003;&#x4E0B;&#x534A;&#x90E8; pre_criteria &#x8655;&#x7406;&#x908F;&#x8F2F;</p>
        <p>pre_criteria=&quot;ABC&quot; -&gt; ABC.result</p>
        <p>pre_criteria=&quot;ABC.abc&quot; -&gt; ABC.abc</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">next_criteria</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left">next_criteria=&quot;tab_condition&quot; , next_criteria=&quot;#radio_result#&quot;</td>
    </tr>
    <tr>
      <td style="text-align:left">group</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left">&#x8209;&#x4F8B; : &#x5169;&#x500B;criteria&#x90FD;&#x8A2D;&#x5B9A;group=&quot;1&quot;
        , &#x5C31;&#x6703;&#x88AB;&#x653E;&#x5728;&#x540C;&#x4E00;&#x884C; ; &#x503C;&#x53EA;&#x8981;&#x76F8;&#x540C;&#x5C31;&#x53EF;
        , &#x4F46;&#x8981;&#x9023;&#x7E8C;&#x7684;&#x624D;&#x6703;&#x88AB;&#x5224;&#x65B7;&#x6210;&#x540C;&#x4E00;&#x884C;</td>
    </tr>
    <tr>
      <td style="text-align:left">pre_criteria_from(old)</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left">ex : &#x627E;&#x5230;&#x4E0A;&#x4E00;&#x5C64;&#x7684;pre_criteria&#x4F86;&#x6E90;</td>
    </tr>
    <tr>
      <td style="text-align:left">pre_criteria_next(old)</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left">&#x627E;&#x5230;&#x4E0A;&#x4E00;&#x5C64;&#x7684;next_criteria</td>
    </tr>
    <tr>
      <td style="text-align:left">pre_criteria_value_specify(old)</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left">ex : &#x9810;&#x8A2D;&#x62FF;result , &#x53EF;&#x6307;&#x5B9A;&#x5176;&#x4ED6;&#x503C;,
        &#x4F8B;&#x5982; : is_base_by</td>
    </tr>
    <tr>
      <td style="text-align:left">pre_criteria_value_is(old)</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left">&#x5224;&#x65B7;&#x5F0F; , = &quot;ture&quot;</td>
    </tr>
  </tbody>
</table>

{% hint style="info" %}
pre\_criteria  處理邏輯

_pre\_criteria_="data\_type"   -&gt; data\_type 只要是任意值 , 即可通過

pre\_criteria="ABC,DEF=123\|456"    -&gt;  DEF的值只要符合123 or 456 , 即可通過



pre\_criteria="ABC,DEF&test123=123\|456"    -&gt;  DEF.test123的值只要符合123 or 456 , 即可通過

pre\_criteria="ABC,DEF=123&456"   -&gt; DEF的值要同時符合123 and 456 , 才能通過
{% endhint %}

