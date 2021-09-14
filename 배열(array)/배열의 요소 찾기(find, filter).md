# 배열의 요소 찾기(검색)
## find
* 문법: arr.find(callback(element[, index[, array]])[, thisArg])
  * callback: 3개의 인수를 취하여 배열의 각 값에 대해 실행할 함수이다.
  * element: 배열에서 처리중인 현재 요소이다.
  * index: 배열에서 처리중인 현재 요소의 인덱스이다.
  * array: find 함수가 호출된 배열이다.
  * thisArg: 콜백을 실행할 때 this로 사용할 객체이다. 
* callback의 조건에 맞는 최초의 요소를 찾으면 해당 요소를, 찾지 못하면 undefined를 반환하고 즉시 종료된다.
<pre>
  <code>
    var arr = [1, 5, 6, 3, 4, 7];
    var find1 = arr.find((element) => element % 2 === 0);
    var find2 = arr.find((element) => element < 0);
    console.log(find1); // 6
    console.log(find2); // undefined
    
    var objArr = [{alphabet: "a", index: 1},{alphabet: "b", index: 2}, {alphabet: "c", index: 3}];
    var find3 = objArr.find((element)=> element.index === 2);
    console.log(find3) // {alphabet: "b", index: 2}
  </code>
</pre>

## filter