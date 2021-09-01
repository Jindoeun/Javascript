# 문자열(string) 메서드
## 특정 위치의 문자열 알아내기
* charAt  
   * 문법: str.charAt(index)  
   * 문자열에서 특정 인덱스에 위치하는 문자를 가져오는 메서드이다.  
  <pre>
    <code>
      var str = "abcdefghi";
      
      str.charAt(1); // "b"
      str.charAt(9); // "" (index가 문자열의 길이보다 길 경우, 빈문자열을 반환)
      str.charAt(str.length-1); // "i"
      str.charAt(-1); // "" (index가 음수일 경우, 빈문자열을 반환)
      str.charAt(); // "a" (index를 생략하면 기본값으로 0를 설정되어 첫문자를 반환)
    </code>
  </pre>

## 부분 문자열 가져오기(자르기)
* substring 
  * 문법: str.substring(start[, end])  
  * 문자열의 start부터 end 전까지 문자열의 부분 문자열을 반환하는 메서드이다. 
* substr 
  * 문법: str.substr(start[, length])  
  * 문자열에서 start에서 시작하여 length 갯수 만큼의 문자들을 반환한다. 
* slice  
  * 문법: str.slice(start[, end])  
  * 문자열의 start부터 end 전까지 문자열의 부분  새로운 문자열을 반환한다.  
  <pre>
    <code>
      var str = "abcdefghi";

      str.substring(1, 3); // "bc"
      str.substr(1, 3); // "bcd"
      str.slice(1, 3) // "bc"
      str.substring(3); // "defghi" (end가 생략될 경우, 끝까지 반환)
      str.substr(3); // "defghi" (length가 생략될 경우, 끝까지 반환)
      str.slice(3); // "defghi" (end가 생략될 경우, 끝까지 반환)
      str.substring(-4); // "fghi" (음수를 입력할 경우, 뒤에서부터 음수의 절대값만큼 거꾸로 계산하여 반환)
      str.subslice(-4); // "fghi" (음수를 입력할 경우, 뒤에서부터 음수의 절대값만큼 거꾸로 계산하여 반환)
    </code>
  </pre>

## Reference
substring과 slice의 차이점은 무엇일까?  
* start가 end보다 클 경우
<pre>
  <code>
    var str = "abcdefghi";
    str.substring(3, 1); // "bc" (start 값과 end 값을 바꾸어서 처리 -> substring(1, 3))
    str.slice(3, 1) // "" (빈문자열을 반환)
  </code>
</pre>
* start 또는 end가 음수일 경우  
  substring은 음수는 0으로 계산한다.  
  slice는 string의 가장 뒤에서 음수의 절대값만큼 거꾸로 계산하여 반환한다.
<pre>
  <code>
    var str = "abcdefghi";

    str.substring(-4); // "abcdefghi" (str.substring(0))
    str.substring(-4, -2); // "" (str.substring(0, 0))
    str.substring(0, -2); // "" (str.substring(0, 0))
    str.substring(-4); // "abcdefghi" (str.substring(0))

    str.slice(-4); // "fg"
    str.slice(-4, -2); // "fghi"
    str.slice(0, -2); // "abcdefg"
  </code>
</pre>

## 문자열 검색하기
* indexOf
  * 문법: str.indexOf(searchValue[, fromIndex])
  * 문자열에서 searchValue를 fromIndex 위치부터(생략했을 시 0부터) 탐색하여, 일치하는 첫 번째 인덱스를 반환한다.
  * 일치하는 값이 없으면 -1을 반환한다.
* lastIndexOf
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
