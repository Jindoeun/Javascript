# 문자열 반복하기
## repeat
  * 문법: str.repeat(count)
  * str을 count 횟수만큼 반복해서 반환해주는 메서드이다.
  * count
    * 문자열을 반복할 횟수이다.
    * 0 <= count < Infinity 의 범위에 있어야하며, 정수가 아닐 경우 내림(integer)된다.
  * **IE에선 작동하지 않는다.**
  <pre>
    <code>
    'ab'.repeat(3); // 'ababab'
    'ab'.repeat(0); // ''
    'ab'.repeat(3.9); // 'ababab'
    'ab'.repeat(-3); // Error
    'ab'.repeat(3/0); // Error (3/0 = Infinity)
    'ab'.repeat(); // ''
    </code>
  </pre>