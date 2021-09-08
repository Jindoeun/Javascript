# 문자열 검색하기
## indexOf
  * 문법: str.indexOf(searchValue[, fromIndex])
  * 문자열에서 searchValue를 fromIndex 위치부터(생략했을 시 0부터) 탐색하여, 일치하는 첫 번째 인덱스를 반환한다.
  * 일치하는 값이 없으면 -1을 반환한다.
## lastIndexOf
  * 문법: str.lastIndexOf(searchValue[, searchValue])
  *  문자열에서 searchValue를 fromIndex 위치부터 역순으로 탐색하여, 일치하는 첫 번쨰  인덱스를 반환합니다.
  * 일치하는 값이 없으면 -1을 반환한다.
  * fromIndex >= str.length인 경우 모든 문자열을 탐색합니다. fromIndex이 음수인 경우엔 0을 지정한 것과 동일합니다.
  <pre>
    <code>
    var str = "abcdabc";

    str.indexOf('ab'); // 0
    str.indexOf('ac'); // -1
    str.indexOf('ab', 0); // 5
    str.indexOf('ab', 4); // 5
    str.indexOf('ab', 5); // -1
    str.indexOf(''); // 0

    str.lastIndexOf('a'); // 4
    str.lastIndexOf('a', 2); // 1
    str.lastIndexOf('c', 1); // -1
    str.lastIndexOf('f'); // -1
    str.lastIndexOf('a', -5); // 0
    str.lastIndexOf('a', 0); // 0
    str.lastIndexOf(''); // 7
    </code>
  </pre>