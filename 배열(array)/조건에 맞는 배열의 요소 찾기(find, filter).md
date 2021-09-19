# 배열의 요소 찾기(검색)
## find
* 문법: array.find(callback(element[, index[, array]])[, thisArg])
  * callback: array에서 찾고싶은 요소를 가지고 있는 함수이다.
  * element: 배열에서 처리중인 현재 요소이다.
  * index: 배열에서 처리중인 현재 요소의 인덱스이다.
  * array: find 함수가 호출된 배열이다.
  * thisArg: callback을 실행할 때 this로 사용할 객체이다. 
* callback의 조건에 맞는 **최초의 요소**를 찾으면 해당 요소를, 찾지 못하면 undefined를 반환하고 즉시 종료된다.
<pre>
  <code>
  var arr = [1, 5, 6, 3, 4];
  
  var funParameters = arr.find((num, index, arr) => console.log(num, index, arr));
  // 1 0 [1, 5, 6, 3, 4]
  // 5 1 [1, 5, 6, 3, 4]
  // 6 2 [1, 5, 6, 3, 4]
  // 3 3 [1, 5, 6, 3, 4]
  // 4 4 [1, 5, 6, 3, 4]

  var find1 = arr.find(el => el % 2 === 0);
  var find2 = arr.find(el => el < 0);
  console.log(find1); // 6
  console.log(find2); // undefined
  
  var objArr = [{alphabet: "a", index: 1},{alphabet: "b", index: 2}, {alphabet: "c", index: 3}];
  var find3 = objArr.find(el=> el.index === 2);
  console.log(find3) // {alphabet: "b", index: 2}
  </code>
</pre>

## filter
* 문법: array.filter(callback(element[, index[, array]])[, thisArg])
  * callback: array에서 찾고 싶은 요소를 가지고 있는 함수이다.
  * element: 배열에서 처리중인 현재 요소이다.
  * index: 배열에서 처리중인 현재 요소의 인덱스이다.
  * array: filter 함수가 호출된 배열이다.
  * thisArg: callback을 실행할 때 this로 사용할 객체이다. 
* callback의 조건에 맞는 **모든 요소**를 찾아 새로운 배열로 반환한다. 조건에 맞는 요소가 없을 경우 빈 배열을 반환한다.
<pre>
  <code>
  var arr1 = [1, 5, 6, 3, 4];

  var funParameters = arr1.filter((num, index, arr1) => console.log(num, index, arr1));
  // 1 0 [1, 5, 6, 3, 4]
  // 5 1 [1, 5, 6, 3, 4]
  // 6 2 [1, 5, 6, 3, 4]
  // 3 3 [1, 5, 6, 3, 4]
  // 4 4 [1, 5, 6, 3, 4]

  var filter1 = arr1.filter(el => el % 2 === 0);
  var filter2 = arr1.filter(el => el < 0);
  console.log(filter1); // [6, 4]
  console.log(filter2); // []

  var arr2 = [
    { id: 15 },
    { id: -1 },
    { id: 0 },
    { id: 3 },
    { id: 12.2 },
    { },
    { id: null },
    { id: NaN },
    { id: 'undefined' }
  ];
  var invalidEntries = 0;
  
  function isNumber(obj) {
    return obj !== undefined && typeof(obj) === 'number' && !isNaN(obj);
  }
  
  function filterByID(item) {
    if (isNumber(item.id) && item.id !== 0) {
      return true;
    }
    invalidEntries++;
    return false;
  }
  
  var arrByID = arr2.filter(filterByID);
  
  console.log('Filtered Array\n', arrByID);
  // Filtered Array
  // [{ id: 15 }, { id: -1 }, { id: 3 }, { id: 12.2 }]
  
  console.log('Number of Invalid Entries = ', invalidEntries);
  // Number of Invalid Entries = 5
  </code>
</pre>