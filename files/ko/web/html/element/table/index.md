---
title: <table>
slug: Web/HTML/Element/table
---

{{HTMLSidebar}}

**HTML `<table>` 요소**는 행과 열로 이루어진 표를 나타냅니다.

{{EmbedInteractiveExample("pages/tabbed/table.html","tabbed-standard")}}

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">
        <a href="/ko/docs/Web/Guide/HTML/Content_categories">콘텐츠 카테고리</a>
      </th>
      <td>
        <a href="/ko/docs/Web/Guide/HTML/Content_categories#플로우_콘텐츠"
          >플로우 콘텐츠</a
        >.
      </td>
    </tr>
    <tr>
      <th scope="row">가능한 콘텐츠</th>
      <td>
        순서대로,
        <div class="content-models">
          <div id="table-mdls">
            <ol>
              <li>선택적인 {{HTMLElement("caption")}} 요소</li>
              <li>0개 이상의 {{HTMLElement("colgroup")}} 요소</li>
              <li>선택적인 {{HTMLElement("thead")}} 요소</li>
              <li>
                다음 중 하나
                <ul>
                  <li>0개 이상의 {{HTMLElement("tbody")}} 요소</li>
                  <li>0개 이상의 {{HTMLElement("tr")}} 요소</li>
                </ul>
              </li>
              <li>선택적인 {{HTMLElement("tfoot")}} 요소</li>
            </ol>
          </div>
        </div>
      </td>
    </tr>
    <tr>
      <th scope="row">태그 생략</th>
      <td>{{no_tag_omission}}</td>
    </tr>
    <tr>
      <th scope="row">가능한 부모 요소</th>
      <td>
        <a href="/ko/docs/Web/Guide/HTML/Content_categories#플로우_콘텐츠"
          >플로우 콘텐츠</a
        >를 허용하는 모든 요소.
      </td>
    </tr>
    <tr>
      <th scope="row">가능한 ARIA 역할</th>
      <td>모두</td>
    </tr>
    <tr>
      <th scope="row">DOM 인터페이스</th>
      <td>{{domxref("HTMLTableElement")}}</td>
    </tr>
  </tbody>
</table>

## 특성

이 요소는 [전역 특성](/ko/docs/Web/HTML/Global_attributes)만 포함합니다.

### Deprecated attributes

- {{htmlattrdef("align")}} {{Deprecated_inline}}

  - : This enumerated attribute indicates how the table must be aligned inside the containing document. It may have the following values:</p>

    - `left`: the table is displayed on the left side of the document;
    - `center`: the table is displayed in the center of the document;
    - `right`: the table is displayed on the right side of the document.

    Set {{cssxref("margin-left")}} and {{cssxref("margin-right")}} to `auto` or {{cssxref("margin")}} to `0 auto` to achieve an effect that is similar to the align attribute.

- {{htmlattrdef("bgcolor")}} {{Deprecated_inline}}

  - : The background color of the table. It is a [6-digit hexadecimal RGB code](/ko/docs/Web/CSS/color_value#RGB_colors), prefixed by a '`#`'. One of the predefined [color kewords](/ko/docs/Web/CSS/color_value#Color_keywords) can also be used.

    To achieve a similar effect, use the CSS {{cssxref("background-color")}} property.

- {{htmlattrdef("border")}} {{Deprecated_inline}}

  - : This integer attribute defines, in pixels, the size of the frame surrounding the table. If set to 0, the [`frame`](/ko/docs/Web/HTML/Element/table#frame) attribute is set to void.
    To achieve a similar effect, use the CSS {{cssxref("border")}} shorthand property.

- {{htmlattrdef("cellpadding")}} {{Deprecated_inline}}

  - : This attribute defines the space between the content of a cell and its border, displayed or not. If the cellpadding's length is defined in pixels, this pixel-sized space will be applied to all four sides of the cell's content. If the length is defined using a percentage value, the content will be centered and the total vertical space (top and bottom) will represent this value. The same is true for the total horizontal space (left and right).

    To achieve a similar effect, apply the {{cssxref("border-collapse")}} property to the `<table>` element, with its value set to collapse, and the {{cssxref("padding")}} property to the {{HTMLElement("td")}} elements.

- {{htmlattrdef("cellspacing")}} {{Deprecated_inline}}

  - : This attribute defines the size of the space between two cells in a percentage value or pixels. The attribute is applied both horizontally and vertically, to the space between the top of the table and the cells of the first row, the left of the table and the first column, the right of the table and the last column and the bottom of the table and the last row.

    To achieve a similar effect, apply the {{cssxref("border-spacing")}} property to the `<table>` element. `border-spacing` does not have any effect if {{cssxref("border-collapse")}} is set to collapse.

- {{htmlattrdef("frame")}} {{Deprecated_inline}}

  - : This enumerated attribute defines which side of the frame surrounding the table must be displayed.

    To achieve a similar effect, use the {{cssxref("border-style")}} and {{cssxref("border-width")}} properties.

- {{htmlattrdef("rules")}} {{Deprecated_inline}}

  - : This enumerated attribute defines where rules, i.e. lines, should appear in a table. It can have the following values:

    - `none`, which indicates that no rules will be displayed; it is the default value;
    - `groups`, which will cause the rules to be displayed between row groups (defined by the {{HTMLElement("thead")}}, {{HTMLElement("tbody")}} and {{HTMLElement("tfoot")}} elements) and between column groups (defined by the {{HTMLElement("col")}} and {{HTMLElement("colgroup")}} elements) only;
    - `rows`, which will cause the rules to be displayed between rows;
    - `columns`, which will cause the rules to be displayed between columns;
    - `all`, which will cause the rules to be displayed between rows and columns.

    To achieve a similar effect, apply the {{cssxref("border")}} property to the appropriate {{HTMLElement("thead")}}, {{HTMLElement("tbody")}}, {{HTMLElement("tfoot")}}, {{HTMLElement("col")}}, or {{HTMLElement("colgroup")}} elements.

- {{htmlattrdef("summary")}} {{Deprecated_inline}}
  - : This attribute defines an alternative text that summarizes the content of the table. Use the {{htmlelement("caption")}} element instead.
- {{htmlattrdef("width")}} {{Deprecated_inline}}
  - : This attribute defines the width of the table. Use the CSS {{cssxref("width")}} property instead.

## 예제

### 간단한 표

```html
<table>
  <tr>
    <td>John</td>
    <td>Doe</td>
  </tr>
  <tr>
    <td>Jane</td>
    <td>Doe</td>
  </tr>
</table>
```

{{ EmbedLiveSample('간단한_표', '100%', '100') }}

### 추가 예제

```html
<p>Simple table with header</p>
<table>
  <tr>
    <th>First name</th>
    <th>Last name</th>
  </tr>
  <tr>
    <td>John</td>
    <td>Doe</td>
  </tr>
  <tr>
    <td>Jane</td>
    <td>Doe</td>
  </tr>
</table>

<p>Table with thead, tfoot, and tbody</p>
<table>
  <thead>
    <tr>
      <th>Header content 1</th>
      <th>Header content 2</th>
    </tr>
  </thead>
  <tfoot>
    <tr>
      <td>Footer content 1</td>
      <td>Footer content 2</td>
    </tr>
  </tfoot>
  <tbody>
    <tr>
      <td>Body content 1</td>
      <td>Body content 2</td>
    </tr>
  </tbody>
</table>

<p>Table with colgroup</p>
<table>
  <colgroup span="4" class="columns"></colgroup>
  <tr>
    <th>Countries</th>
    <th>Capitals</th>
    <th>Population</th>
    <th>Language</th>
  </tr>
  <tr>
    <td>USA</td>
    <td>Washington D.C.</td>
    <td>309 million</td>
    <td>English</td>
  </tr>
  <tr>
    <td>Sweden</td>
    <td>Stockholm</td>
    <td>9 million</td>
    <td>Swedish</td>
  </tr>
</table>

<p>Table with colgroup and col</p>
<table>
  <colgroup>
    <col class="column1" />
    <col class="columns2plus3" span="2" />
  </colgroup>
  <tr>
    <th>Lime</th>
    <th>Lemon</th>
    <th>Orange</th>
  </tr>
  <tr>
    <td>Green</td>
    <td>Yellow</td>
    <td>Orange</td>
  </tr>
</table>

<p>Simple table with caption</p>
<table>
  <caption>
    Awesome caption
  </caption>
  <tr>
    <td>Awesome data</td>
  </tr>
</table>
```

```css hidden
table {
  border-collapse: collapse;
  border-spacing: 0px;
}
table,
th,
td {
  padding: 5px;
  border: 1px solid black;
}
```

{{ EmbedLiveSample('추가_예제', '100%', '700') }}

## 접근성 고려사항

### 설명문

표의 목적에 대한 명확하고 상세한 설명을 포함하는 {{HTMLElement("caption")}} 요소를 제공하여 사용자가 표 콘텐츠를 확인할지, 넘어갈지 결정할 때 도움을 줄 수 있습니다.

특히 스크린 리더 등 보조 기술 사용자와 낮은 시력의 사용자, 그리고 인지능력의 저하를 겪고 있는 사용자에게 도움이 됩니다.

- [MDN Adding a caption to your table with \<caption>](/ko/docs/Learn/HTML/Tables/Advanced#Adding_a_caption_to_your_table_with_<caption>)
- [Caption & Summary • Tables • W3C WAI Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/tables/caption-summary/)

### 행과 열 범위 지정

간단한 표의 경우 범위를 자동으로 유추할 수 있기 때문에, 헤더 요소의 [`scope`](/ko/docs/Web/HTML/Element/th#scope) 특성은 불필요합니다. 그러나 일부 보조 기술이 잘못된 범위를 유추하는 경우도 있기 때문에, 범위를 지정하는 것이 사용자 경험에 도움이 될 수도 있습니다. 복잡한 표에서는 범위를 명시해서 특정 헤더와 연관된 칸에 대한 정보를 제공할 수 있습니다.

#### 예제

```html
<table>
  <caption>
    Color names and values
  </caption>
  <tbody>
    <tr>
      <th scope="col">Name</th>
      <th scope="col">HEX</th>
      <th scope="col">HSLa</th>
      <th scope="col">RGBa</th>
    </tr>
    <tr>
      <th scope="row">Teal</th>
      <td><code>#51F6F6</code></td>
      <td><code>hsla(180, 90%, 64%, 1)</code></td>
      <td><code>rgba(81, 246, 246, 1)</code></td>
    </tr>
    <tr>
      <th scope="row">Goldenrod</th>
      <td><code>#F6BC57</code></td>
      <td><code>hsla(38, 90%, 65%, 1)</code></td>
      <td><code>rgba(246, 188, 87, 1)</code></td>
    </tr>
  </tbody>
</table>
```

{{htmlelement("th")}} 요소에 `scope="col"`을 선언함으로써, 해당 칸이 열의 맨 위에 위치함을 설명할 수 있습니다. 마찬가지로, `scope="row"`를 추가하면 해당 칸이 행의 맨 앞에 위치함을 설명합니다.

- [MDN Tables for visually impaired users](/ko/docs/Learn/HTML/Tables/Advanced#Tables_for_visually_impaired_users)
- [Tables with two headers • Tables • W3C WAI Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/tables/two-headers/)
- [Tables with irregular headers • Tables • W3C WAI Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/tables/irregular/)
- [H63: Using the scope attribute to associate header cells and data cells in data tables | W3C Techniques for WCAG 2.0](https://www.w3.org/TR/WCAG20-TECHS/H63.html)

### 복잡한 표

너무나 복잡해서 헤더 칸을 확실히 가로 또는 세로로 연결할 수 없는 표의 경우, 스크린 리더와 같은 보조 기술이 분석할 때 어려움을 겪을 수 있습니다. 보통 [`colspan`](/ko/docs/Web/HTML/Element/td#colspan)과 [`rowspan`](/ko/docs/Web/HTML/Element/td#rowspan) 특성이 존재하는 경우 이 정도로 복잡한 표라고 할 수 있습니다.

이상적으로 보자면, 테이블의 콘텐츠를 나타내는 다른 방법을 생각하는 것이 좋습니다. 이를테면 서로 관련된 더 작은 표로 나눠서 `colspan`, `rowspan` 특성의 필요를 제거하는 것입니다. 보조 기술 사용자의 테이블 콘텐츠 이해에 도움을 줄 뿐 아니라, 인지력 문제를 겪고 있어 기존 표의 레이아웃을 이해하는 것이 곤란한 사용자의 경험도 개선할 수 있습니다.

표를 나눌 수 없는 경우 [`id`](/ko/docs/Web/HTML/Global_attributes#id)와 [`headers`](/ko/docs/Web/HTML/Element/td#headers) 특성을 통해 표의 각 칸을 연관된 헤더 칸과 직접 연결하세요.

- [MDN Tables for visually impaired users](/ko/docs/Learn/HTML/Tables/Advanced#Tables_for_visually_impaired_users)
- [Tables with multi-level headers • Tables • W3C WAI Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/tables/multi-level/)
- [H43: Using id and headers attributes to associate data cells with header cells in data tables | Techniques for W3C WCAG 2.0](https://www.w3.org/TR/WCAG20-TECHS/H43.html)

## 명세

{{Specifications}}

## 브라우저 호환성

{{Compat}}

## 같이 보기

- `<table>` 요소 스타일링에 특히 도움이 되는 CSS 속성

  - 표의 너비를 조절하는 {{cssxref("width")}}.
  - 표의 테두리를 설정하는 {{cssxref("border")}}, {{cssxref("border-style")}}, {{cssxref("border-color")}}, {{cssxref("border-width")}}, {{cssxref("border-collapse")}}, {{cssxref("border-spacing")}}.
  - 각 칸의 콘텐츠를 꾸밀 때 사용할 수 있는 {{cssxref("margin")}}, {{cssxref("padding")}}.
  - 각 칸의 텍스트와 콘텐츠를 정렬할 때 사용하는 {{cssxref("text-align")}}, {{cssxref("vertical-align")}}.
