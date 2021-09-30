# 일부 문자열 수정하기
## replace
  * 문법: str.replace(substr, newSubstr)
  * str에서 substr을 검색하여 가장 첫번째로 발견한 subStr을 newSubstr로 수정하여 반환해주는 메서드이다.
  * 기존 str을 수정하지 않는다.
  * substr: 수정하고 싶은 문자열 또는 정규식
  * newSubstr: 대체하고 싶은 문자열 또는 대체할 문자를 생성할 함수
  <pre>
    <code>
    var str = "Apple is red. But, green apple is green."
    var newStr = str.replace('apple', 'grape'); // Apple is red. But, Green grape is green.
    </code>
  </pre>