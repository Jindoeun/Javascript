# 배열의요소 추가
## push
* 문법: array.push(element1[, ...[, elementN]]))  
* 배열의 맨끝에 element를 추가하는 메서드이다.
* 여러개도 가능하다.
* 배열의 길이를 반환한다.  
* push로 두 배열을 합칠수도 있다.
  * 두번째 배열의 모든 엘리먼트를 push 하기 위해 apply()를 사용한다.
  * 그러나 만약 두번째 배열(아래 예제에서는 arr2)이 매우 클 경우, 이 메소드를 사용하지 말아야 한다. 실제로 한 함수가 사용가능한 매개변수의 최대 개수에는 제한이 있기 때문이다.
<pre>
  <code>
    var arr = ["a", "b"];
    arr.push("c"); // 3
    console.log(arr); // ["a", "b", "c"]
    arr.push("d", "e"); // 5
    console.log(arr); // ["a", "b", "c", "d", "e"]

    var arr1 = ["a", "b"];
    var arr2 = ["c", "d", "e"];
    Array.prototype.push.apply(arr1, arr2);
    // 첫번째 배열에 두번째 배열을 합친다.
    // arr1.push("c", "d", "e"); 하는 것과 동일하다.
    console.log(arr1); // ["a", "b", "c", "d", "e"]
  </code>
</pre>

## unshift
* 문법: array.unshift(element1[, ...[, elementN]]))  
* 배열의 맨앞에 element를 추가하는 메서드이다.
* 여러개도 가능하다.
* 배열의 길이를 반환한다.  
<pre>
  <code>
    var arr = ["d", "e"];

    arr.unshift("c"); // 3
    console.log(arr); // ["c", "d", "e"]

    arr.unshift("a", "b"); // 5
    console.log(arr); // [""a", "b", "c", "d", "e"]
  </code>
</pre>

## splice
* 문법: array.splice(start[, deleteCount[, item1[, item2[, ...]]]])
* 배열의 기존 요소를 삭제 또는 교체하거나 새 요소를 추가해주는 메서드이다.
* 삭제한 요소를 담은 배열을 반환한다. 아무 값도 삭제하지 않았으면 빈 배열을 반환한다.
* start
  * 배열의 변경을 시작할 인덱스
  * 배열의 길이보다 큰 값일 경우 배열의 길이로 설정된다.
  * 음수인 경우 배열의 끝에서부터 음수의 절대값만큼 거꾸로 계산된다. 음수값의 절대값이 배열의 길이 보다 큰 경우 0으로 설정된다.
* deleteCount
  * 배열에서 삭제할 요소의 수입니다.
  * 생략하거나 값이 array.length - start보다 크면 start부터 모든 요소를 삭제한다.
  * deleteCount가 음수라면 어떤 요소도 삭제하지 않는다.
* item1, item2, ...
  * 배열에 추가할 요소이다. 아무 요소도 지정하지 않으면 splice()는 요소를 삭제하기만 한다.
<pre>
  <code>
    // 삭제
    var arr = ["a", "b", "c", "d", "e"];
    arr.splice(1, 3); // ["b", "c", "d"]
    console.log(arr); // ["a", "e"]

    var arr = ["a", "b", "c", "d", "e"];
    arr.splice(2); // ["c", "d", "e"]
    console.log(arr); // ["a", "b"]

    var arr = ["a", "b", "c", "d", "e"];
    arr.splice(-2, 3); // ["d", "e"]
    console.log(arr); // ["a", "b", "c"]

    var arr = ["a", "b", "c", "d", "e"];
    arr.splice(-6, 3); // ["a", "b", "c"] ( => arr.splice(0, 3) )
    console.log(arr); // ["d", "e"]

    var arr = ["a", "b", "c", "d", "e"];
    arr.splice(1, -3); // [] ( => arr.splice(1, 0) )
    console.log(arr); // ["a", "b", "c", "d", "e"]


    // 삭제하지 않고, 추가
    var arr = ["a", "b", "c", "d", "e"];
    arr.splice(1, 0, "aa"); // []
    console.log(arr); // ["a", "aa" "b", "c", "d", "e"]


    // 삭제하고, 그 자리에 추가
    var arr = ["a", "b", "c", "d", "e"];
    arr.splice(1, 3, "aa"); // ["b", "c", "d"]
    console.log(arr); // ["a", "aa", "e"]
  </code>
</pre>