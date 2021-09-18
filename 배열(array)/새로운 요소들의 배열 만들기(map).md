# 새로운 요소들의 배열 만들기
## map
* 문법: array.map(callback(currentValue[, index[, array]])[, thisArg])
  * array.map(x => x에 대해 arrow function);  
  array.map(function(x) { x에 대한 function});
* 반복문을 돌며 배열 안의 요소들을 하나씩 callback 함수의 조건에 맞게 바꾸어 **새로운 배열**을 반환하는 메서드이다.
  * currentValue: 처리할 현재 요소
  * index: 처리할 현재 요소의 인덱스.
  * array: map()을 호출한 배열.
  * thisArg: callback을 실행할 때 this로 사용되는 값.
<pre>
  <code>
  var arr = [1, 2, 3];

  var result = arr.map(x => {
    if (x % 2) {
      return '홀수';
    }
    return '짝수';
  });
  result; // ['홀수', '짝수', '홀수']
  </code>
</pre>


## map과 forEach의 차이점은?
forEach가 배열 요소마다 한 번씩 주어진 함수(콜백)를 실행하는 것과 달리, map은 배열 내의 모든 요소 각각에 대하여 주어진 함수(콜백)를 호출한 결과를 모아 **새로운 배열을 반환한다**는 특징이 있다.  
forEach는 결과로 새로운 배열을 가지기 위해서 배열을 만들어놓고 push를 해주어야한다.
<pre>
  <code>
  var arr = [1, 2, 3];
  var result = [];
  
  arr.forEach(x => {
    if (x % 2) {
      result.push('홀수');
    }
    result.push('짝수');
  });
  result; // ['홀수', '짝수', '홀수']
  </code>
</pre>


## object에서 map 활용
<pre>
  <code>
  var Array = [{key:1, value:10},
              {key:2, value:20},
              {key:3, value: 30}];
             
  var result = Array.map(function(el){ 
    var obj = {};
    obj[el.key] = el.value;
    return obj;
  });
  result; // [{1:10}, {2:20}, {3:30}]


  var obj = {'a': 1, 'b': 2, 'c': 3};

  Object.keys(obj).map(x => {
    obj[x] *= 2;
  });
  obj; // {a: 2, b: 4, c: 6}
  </code>
</pre>
Object.keys(obj)는 obj의 key값을 배열로 반환해주기 떄문에 ['a', 'b', 'c']의 배열이 만들어져 map을 사용할 수 있다.