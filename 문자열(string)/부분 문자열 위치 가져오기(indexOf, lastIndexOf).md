# 문자열 검색하기
## indexOf
* 문법: str.indexOf(searchValue[, fromIndex])
  * fromIndex: 생략했거나 음수인 경우 0부터 탐색하며, str.length보다 크거나 같을 경우 -1을 반환한다.
* 문자열에서 searchValue를 fromIndex 위치부터 탐색하여, 일치하는 첫 번째 인덱스를 반환한다.
* 일치하는 값이 없으면 -1을 반환한다.
<pre>
  <code>
  var str = "abcdabc";

  str.indexOf('ab'); // 0
  str.indexOf('ab', -1); // 0
  str.indexOf('ab', 4); // 4
  str.indexOf('ab', 5); // -1
  str.indexOf('c', 1); // 2
  str.indexOf('ac'); // -1
  str.indexOf(''); // 0
  </code>
</pre>

## lastIndexOf
* 문법: str.lastIndexOf(searchValue[, fromIndex])
  * fromIndex: 생략했거나 str.length보다 크거나 같을 경우 str.length-1 부터, 음수인 경우 0부터 탐색한다.
* 문자열에서 searchValue를 fromIndex 위치부터 역순으로 탐색하여, 일치하는 첫 번째 인덱스를 반환한다.
* 일치하는 값이 없으면 -1을 반환한다.
<pre>
  <code>
  var str = "abcdabc";

  str.lastIndexOf('ab'); // 4
  str.lastIndexOf('ab', -1); // 0
  str.lastIndexOf('ab', 4); // 4
  str.lastIndexOf('ab', 5); // 4
  str.lastIndexOf('c', 1); // -1
  str.lastIndexOf('ac'); // -1
  str.lastIndexOf(''); // 7
  </code>
</pre>