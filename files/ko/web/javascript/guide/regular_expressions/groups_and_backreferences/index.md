---
title: Groups and Ranges
slug: Web/JavaScript/Guide/Regular_expressions/Groups_and_backreferences
---

{{jsSidebar("JavaScript Guide")}}

그룹(Groups)과 범위(ranges)는 표현 문자의 그룹과 범위를 나타냅니다.

## Types

<table class="standard-table">
  <thead>
    <tr>
      <th scope="col">Characters</th>
      <th scope="col">Meaning</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <code><em>x</em>|<em>y</em></code>
      </td>
      <td>
        <p>
          <code>x</code>또는 <code>y</code>와 매칭되는 경우. 예를들면
          <code>/green|red/</code> 은 "green apple"의 "green"과 매치되고 "red
          apple"의 "red"와 매치됩니다.
        </p>
      </td>
    </tr>
    <tr>
      <td>
        <code>[xyz]<br />[a-c]</code>
      </td>
      <td>
        <p>
          A character set. Matches any one of the enclosed characters. You can
          specify a range of characters by using a hyphen, but if the hyphen
          appears as the first or last character enclosed in the square brackets
          it is taken as a literal hyphen to be included in the character set as
          a normal character. It is also possible to include a character class
          in a character set.
        </p>
        <p>
          For example, <code>[abcd]</code> is the same as <code>[a-d]</code>.
          They match the "b" in "brisket" and the "c" in "chop".
        </p>
        <p>
          For example, [abcd-] and [-abcd] match the "b" in "brisket", the "c"
          in "chop" and the "-" (hyphen) in "non-profit".
        </p>
        <p>
          For example, [\w-] is the same as [A-Za-z0-9_-]. They match the "b" in
          "brisket", the "c" in "chop" and the "n" in "non-profit".
        </p>
      </td>
    </tr>
    <tr>
      <td>
        <p>
          <code>[^xyz]<br />[^a-c]</code>
        </p>
      </td>
      <td>
        <p>
          A negated or complemented character set. That is, it matches anything
          that is not enclosed in the brackets. You can specify a range of
          characters by using a hyphen, but if the hyphen appears as the first
          or last character enclosed in the square brackets it is taken as a
          literal hyphen to be included in the character set as a normal
          character. For example, <code>[^abc]</code> is the same as
          <code>[^a-c]</code>. They initially match "o" in "bacon" and "h" in
          "chop".
        </p>
        <div class="blockIndicator note">
          <p>
            The ^ character may also indicate the
            <a
              href="https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/Regular_Expressions/Boundaries"
              >beginning of input</a
            >.
          </p>
        </div>
      </td>
    </tr>
    <tr>
      <td><code>(<em>x</em>)</code></td>
      <td>
        <p>
          <strong>Capturing group: </strong>Matches <code><em>x</em></code> and
          remembers the match. For example, <code>/(foo)/</code> matches and
          remembers "foo" in "foo bar".
        </p>
        <p>
          A regular expression may have multiple capturing groups. In results,
          matches to capturing groups typically in an array whose members are in
          the same order as the left parentheses in the capturing group. This is
          usually just the order of the capturing groups themselves. This
          becomes important when capturing groups are nested. Matches are
          accessed using the index of the the result's elements (<code
            >[1], ..., [n]</code
          >) or from the predefined <code>RegExp</code> object's properties
          (<code>$1, ..., $9</code>).
        </p>
        <p>
          Capturing groups have a performance penalty. If you don't need the
          matched substring to be recalled, prefer non-capturing parentheses
          (see below).
        </p>
        <p>
          <code
            ><a
              href="/ko/docs/Web/JavaScript/Reference/Global_Objects/String/match"
              >String.match()</a
            ></code
          >
          won't return groups if the <code>/.../g</code> flag is set. However,
          you can still use
          <code
            ><a
              href="/ko/docs/Web/JavaScript/Reference/Global_Objects/String/matchAll"
              >String.matchAll()</a
            ></code
          >
          to get all matches.
        </p>
      </td>
    </tr>
    <tr>
      <td>
        <code>\<em>n</em></code>
      </td>
      <td>
        <p>
          Where <code><em>n</em></code> is a positive integer. A back reference
          to the last substring matching the n parenthetical in the regular
          expression (counting left parentheses). For example,
          <code>/apple(,)\sorange\1/</code> matches "apple, orange," in "apple,
          orange, cherry, peach". A complete example follows this table.
        </p>
      </td>
    </tr>
    <tr>
      <td><code>(?&#x3C;Name>x)</code></td>
      <td>
        <p>
          <strong>Named capturing group: </strong>Matches <code>x</code> and
          stores it on the groups property of the returned matches under the
          name specified by <code>&#x3C;Name></code>. The angle brackets
          ('<code>&#x3C;</code>' and '<code>></code>') are required for group
          name.
        </p>
        <p>
          For example, to extract the United States area code from a phone
          number, I could use <code>/\((?&#x3C;area>\d\d\d)\)/</code>. The
          resulting number would appear under <code>matches.groups.area</code>.
        </p>
      </td>
    </tr>
    <tr>
      <td><code>(?:<em>x</em>)</code></td>
      <td>
        <strong>Non-capturing group: </strong>Matches
        <code><em>x</em></code> but does not remember the match. The matched
        substring cannot be recalled from the resulting array's elements (<code
          >[1], ..., [n]</code
        >) or from the predefined <code>RegExp</code> object's properties (<code
          >$1, ..., $9</code
        >).
      </td>
    </tr>
  </tbody>
</table>

## See also

- A polyfill of [`RegExp` named capture groups](https://github.com/zloirock/core-js#ecmascript-string-and-regexp) is available in [`core-js`](https://github.com/zloirock/core-js)
- [Regular expressions guide](/ko/docs/Web/JavaScript/Guide/Regular_Expressions)

  - [Character classes](/ko/docs/Web/JavaScript/Guide/Regular_Expressions/Character_Classes)
  - [Assertions](/ko/docs/Web/JavaScript/Guide/Regular_Expressions/Assertions)
  - [Quantifiers](/ko/docs/Web/JavaScript/Guide/Regular_Expressions/Quantifiers)
  - [Unicode property escapes](/ko/docs/Web/JavaScript/Guide/Regular_Expressions/Unicode_Property_Escapes)

- [The `RegExp()` constructor](/ko/docs/Web/JavaScript/Reference/Global_Objects/RegExp)
- [ClassRanges in the ECMAScript specification](https://tc39.es/ecma262/multipage/text-processing.html#sec-classranges)
