# 특정 위치의 문자열 알아내기
## charAt  
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