# 일부 문자열 수정하기
## replace
* str에서 substr을 검색하여 가장 첫번째로 발견한 subStr을 newSubstr로 수정하여 반환해주는 메서드이다.
* 문법: str.replace(substr, newSubstr)
* substr: 수정하고 싶은 문자열 또는 정규식
* newSubstr: 대체하고 싶은 문자열 또는 대체할 문자를 생성할 함수
* 기존 str을 수정하지 않으며, 대소문자를 구분한다.
<pre>
  <code>
  var str = "Apple is red. But there are green apple and yellow apple."
  str.replace('apple', 'grape'); // Apple is red. But there are green grape and yellow apple.
  </code>
</pre>

# replaceAll 구현하기
js에서는 replaceAll 메서드가 없다. 때문에 정규식으로 이를 대체해야 한다.
정규식에서 g는 모든 값에 대한 검사, i는 대소문자 구분 안함을 뜻한다.
<pre>
  <code>
  var str = "Apple is red. But there are green apple and yellow apple."
  str.replace(/apple/g, 'grape'); // Apple is red. But there are green grape and yellow grape.
  str.replace(/apple/gi, 'grape'); // grape is red. But there are green grape and yellow grape.
  </code>
</pre>