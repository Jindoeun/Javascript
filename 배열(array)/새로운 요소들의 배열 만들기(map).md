# 새로운 요소들의 배열 만들기
## map
* 문법: array.map(callback(currentValue[, index[, array]])[, thisArg])
* 반복문을 돌며 배열 안의 요소들을 하나씩 callback 함수의 조건에 맞게 바꾸어 **새로운 배열**을 반환하는 메서드이다.
  * currentValue: 처리할 현재 요소
  * index: 처리할 현재 요소의 인덱스.
  * array: map()을 호출한 배열.
  * thisArg: callback을 실행할 때 this로 사용되는 값.
<pre>
  <code>
  var oneTwoThree = [1, 2, 3];

  result = oneTwoThree.map((current) => {
    if (current % 2) {
      return '홀수';
    }
    return '짝수';
  });
  result; // ['홀수', '짝수', '홀수']
  </code>
</pre>