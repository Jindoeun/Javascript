# 조건에 맞는 배열의 요소가 있는지 확인
## every
* 문법: array.every(callback(currentValue, currentIndex, array), thisValue))
  * callback: 배열의 각 요소에 대해 실행할 함수로 다음 세 가지 인수를 받는다.
  * currentValue: callback에서 실행할 현재 요소이다.
  * currentIndex: callback에서 실행할 현재 요소의 인덱스이다.
  * array: every를 호출한 배열이다.
  * thisValue: callback에서 this로 사용할 값이다.
* 배열의 요소에 callback을 실행했을 때 **모든** 요소가 true를 반환하는지 확인하는 메서드이다. 연산자로 생각하면 AND(&&)와 같다.
* 모든 요소가 ture를 반환하면 true를 반환한다. 하나라도 false를 반환하는 요소를 찾았을 시, false를 반환하고 즉시 배열 순환을 멈춘다.
* 빈 배열에서 호출하면 무조건 true를 반환하며, 기존 배열을 수정하지 않는다.
* every가 순환하면서 요소가 수정, 추가, 삭제됐을 경우
  * 요소가 수정됐을 경우, currenValue로 되기 전에 수정한 값은 반영되어 처리된다.
  * 요소가 추가됐을 경우, 배열의 길이가 늘어나도 every가 순환하기 전에 배열의 길이만큼 순환한다.
  * 요소가 삭제됐을 경우, 삭제된 배열의 길이만큼 순환한다.
<pre>
  <code>
    var objArr = [{toy: "robot", price: 8000}, {toy: "doll", price: 5000}, {toy: "water gun", price: 2000}]
    
    objArr.every((current)=> current.price < 5000); // false
    objArr.every((current)=> current.price > 1000); // true


    // 화살표 함수 사용
    [12, 5, 8, 130, 44].every(current => current >= 10); // false
    [12, 54, 18, 130, 44].every(current => current >= 10); // true


    // 요소 수정
    var arr = [1, 2, 3, 4];
    arr.every((current, index, array) => {
      arr[index+1] -= 1
      console.log(current, index, array)
      return current < 2
    });
    // 1 0 [1, 1, 3, 4]
    // 1 1 [1, 1, 2, 4]
    // 2 2 [1, 1, 2, 3]
    // false


    // 요소 추가
    var arr = [1, 2, 3, 4];
    arr.every((current, index, array) => {
    if(index >= 1) arr.splice(2, 0, 0);
      console.log(current, index, array);
      return current < 3
    });
    // 1 0 [1, 2, 3, 4]
    // 2 1 [1, 2, 0, 3, 4]
    // 0 2 [1, 2, 0, 0, 3, 4]
    // 0 3 [1, 2, 0, 0, 0, 3, 4]
    // true


    // 요소 삭제
    var arr = [1, 2, 3, 4];
    arr.every((current, index, array) => {
    if(index >= 1) arr.splice(0, 1);
      console.log(current, index, array);
      return current < 4
    });
    // 1 0 [1, 2, 3, 4]
    // 2 1 [2, 3, 4]
    // 4 2 [3, 4]
    // false
  </code>
</pre>

## some
* 문법: array.some(callback(currentValue, currentIndex, array), thisValue))
  * callback: 배열의 각 요소에 대해 실행할 함수로 다음 세 가지 인수를 받는다.
  * currentValue: callback에서 실행할 현재 요소이다.
  * currentIndex: callback에서 실행할 현재 요소의 인덱스이다.
  * array: some을 호출한 배열이다.
  * thisValue: callback에서 this로 사용할 값이다.
* 배열의 요소에 callback을 실행했을 때 **하나의 요소**라도 true를 반환하는지 확인하는 메서드이다. 연산자로 생각하면 OR(||)과 같다.
* 하나의 요소라도 ture를 반환하면 true를 반환하고 즉시 배열 순환을 멈춘다. 모든 요소가 false를 반환했을 시, false를 반환한다.
* 빈 배열에서 호출하면 무조건 true를 반환하며, 기존 배열을 수정하지 않는다.
* some이 순환하면서 요소가 수정, 추가, 삭제됐을 경우(every와 같다.)
  * 요소가 수정됐을 경우, currenValue로 되기 전에 수정한 값은 반영되어 처리된다.
  * 요소가 추가됐을 경우, 배열의 길이가 늘어나도 every가 순환하기 전에 배열의 길이만큼 순환한다.
  * 요소가 삭제됐을 경우, 삭제된 배열의 길이만큼 순환한다.
<pre>
  <code>
    var objArr = [{toy: "robot", price: 8000}, {toy: "doll", price: 5000}, {toy: "water gun", price: 2000}]
    
    objArr.some((current)=> current.price < 5000); // true
    objArr.some((current)=> current.price > 10000); // false


    // 화살표 함수 사용
    [12, 5, 8, 130, 44].some(current => current >= 10); // true
    [12, 54, 18, 130, 44].some(current => current <= 10); // false


    // 요소 수정
    var arr = [1, 2, 3, 4];
    arr.some((current, index, array) => {
      arr[index+1] += 1
      console.log(current, index, array)
      return current > 3
    });
    // 1 0 [1, 3, 3, 4]
    // 3 1 [1, 3, 4, 4]
    // 4 2 [1, 3, 4, 5]
    // true


    // 요소 추가
    var arr = [1, 2, 3, 4];
    arr.some((current, index, array) => {
    if(index >= 1) arr.splice(2, 0, 0);
      console.log(current, index, array);
      return current < 0
    });
    // 1 0 [1, 2, 3, 4]
    // 2 1 [1, 2, 0, 3, 4]
    // 0 2 [1, 2, 0, 0, 3, 4]
    // 0 3 [1, 2, 0, 0, 0, 3, 4]
    // false


    // 요소 삭제
    var arr = [1, 2, 3, 4];
    arr.some((current, index, array) => {
    if(index >= 1) arr.splice(0, 1);
      console.log(current, index, array);
      return current > 4
    });
    // 1 0 [1, 2, 3, 4]
    // 2 1 [2, 3, 4]
    // 4 2 [3, 4]
    // false
  </code>
</pre>