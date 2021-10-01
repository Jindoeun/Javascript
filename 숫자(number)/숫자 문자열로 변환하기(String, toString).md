# 문자로 변환하기
## String  
* 문법: String(value)  
* type이 Number인 숫자를 문자열로 변환시켜 반환해주는 함수이다.
* ``value + ""`` 의 동작을 해주는 함수이므로 undefined나 null을 입력해도 문자로 바꿔준다.
<pre>
  <code>
  String(12.34); // '12.34'
  String(12.34 + 'abc'); // '12.34abc'
  String('abc' + 12.34); // 'abc12.34'
  String(undefined); // 'undefined'
  String(null); // 'null'
  </code>
</pre>

## toString  
* 문법: (value).toString([radix]) 
* type이 Number인 숫자를 문자열로 변환시켜 반환해주는 메서드이다.
* undefined나 null과 같이 값이 없을 경우 Error가 뜬다.
* radix: value를 다른 진수로 바꾸어 문자로 바꾸고싶을 때 사용한다. 2 ~ 36진수까지를 정의할 수 있고, 따로 radix를 지정하지 않을 경우 value 그대로 문자로 변환한다. 범위를 벗어난 진수를 지정할 경우 Error가 뜬다.
<pre>
  <code>
  (12.34).toString(); // '12.34'
  (12.34).toString(5); // '22.1322222222222222222222'
  (12.34 + 'abc').toString(); // '12.34abc'
  ('abc' + 12.34).toString(); // 'abc12.34'
  (undefined).toString(); // Error
  (null).toString(); // Error
  </code>
</pre>

## 덧셈 이용하기
숫자 + 문자열은 문자열이다.
<pre>
  <code>
  12.34 + ""; // "12.34
  </code>
</pre>