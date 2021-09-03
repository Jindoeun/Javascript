# 배열(array) 메서드
## 배열의 요소 추가
* push
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
      var count1 = arr.push("c");
      console.log(count1); // 3
      console.log(arr); // ["a", "b", "c"]
      var count2 = arr.push("d", "e");
      console.log(count); // 5
      console.log(arr); // ["a", "b", "c", "d", "e"]

      var arr1 = ["a", "b"];
      var arr2 = ["c", "d", "e"];

      // 첫번째 배열에 두번째 배열을 합친다.
      // arr1.push("c", "d", "e"); 하는 것과 동일하다.
      Array.prototype.push.apply(arr1, arr2);

      console.log(arr1); // ["a", "b", "c", "d", "e"]
    </code>
  </pre>
* unshift
  * 문법: array.unshift(element1[, ...[, elementN]]))  
  * 배열의 맨앞에 element를 추가하는 메서드이다.
  * 여러개도 가능하다.
  * 배열의 길이를 반환한다.  
  <pre>
    <code>
      var arr = ["d", "e"];

      var count1 = arr.unshift("c");
      console.log(count1); // 3
      console.log(arr); // ["c", "d", "e"]

      var count1 = arr.unshift("a", "b");
      console.log(count2); // 5
      console.log(arr); // [""a", "b", "c", "d", "e"]
    </code>
  </pre>

## 배열의 요소 제거
* pop 
  * 문법: array.pop()  
  * 배열의 맨끝에 요소를 제거하는 메서드이다.
  * 제거된 요소를 반환한다.  
  * 빈 배열에 pop을 호출하면 undefined를 반환한다. 
  <pre>
    <code>
      var arr = ["a", "b", "c", "d", "e"];
      var element = arr.pop();
      console.log(element); // "e"
      console.log(arr); // ["a", "b", "c", "d"]
    </code>
  </pre>
* shift
  * 문법: array.shift()  
  * 배열의 맨앞에 요소를 제거하는 메서드이다.
  * 제거된 요소를 반환한다. 빈 배열에 shift를 호출하면 undefined를 반환한다.   
  <pre>
    <code>
      var arr = ["a", "b", "c", "d", "e"];
      
      var element = arr.shift();
      console.log(element); // "a"
      console.log(arr); // ["b", "c", "d", "e"]
    </code>
  </pre>
* splice
  * 문법: array.splice(start[, deleteCount[, item1[, item2[, ...]]]])
  * 배열의 기존 요소를 삭제 또는 교체하거나 새 요소를 추가해주는 메서드이다.
  * 제거한 요소를 담은 배열을 반환한다. 아무 값도 제거하지 않았으면 빈 배열을 반환한다.
  * start
    * 배열의 변경을 시작할 인덱스
    * 배열의 길이보다 큰 값일 경우 배열의 길이로 설정된다.
    * 음수인 경우 배열의 끝에서부터 음수의 절대값만큼 거꾸로 계산된다. 음수값의 절대값이 배열의 길이 보다 큰 경우 0으로 설정된다.
  * deleteCount
    * 배열에서 제거할 요소의 수입니다.
    * 생략하거나 값이 array.length - start보다 크면 start부터 모든 요소를 제거합니다.
    * deleteCount가 음수라면 어떤 요소도 제거하지 않습니다. 이 때는 최소한 하나의 새로운 요소(item1)를 지정해야 합니다.
  * item1, item2, ...
    * 배열에 추가할 요소입니다. 아무 요소도 지정하지 않으면 splice()는 요소를 제거하기만 합니다.
  <pre>
    <code>
      // 제거
      var arr1 = ["a", "b", "c", "d", "e"];
      arr.splice(1, 3); // ["a", "e"]
      console.log(removeArr); // ["b", "c", "d"]

      var arr1 = ["a", "b", "c", "d", "e"];
      arr.splice(2); // ["d", "e"]
      console.log(removeArr); // ["a", "b", "c"]

      var arr1 = ["a", "b", "c", "d", "e"];
      arr.splice(-2, 3); // ["a", "b", "c"]
      console.log(removeArr); // ["d", "e"]

      var arr1 = ["a", "b", "c", "d", "e"];
      arr.splice(-6, 3); // ["d", "e"] ( => arr.splice(0, 3) )
      console.log(removeArr); // ["a", "b", "c"]

      var arr1 = ["a", "b", "c", "d", "e"];
      arr.splice(1, -3); // ["a", "b", "c", "d", "e"] ( => arr.splice(1, 0) )
      console.log(removeArr); // []


      // 제거하지 않고, 추가
      var arr2 = ["a", "b", "c", "d", "e"];
      arr.splice(1, 0, "aa"); // ["a", "aa" "b", "c", "d", "e"]
      console.log(addArr); // []


      // 제거하고, 그 자리에 추가
      var arr2 = ["a", "b", "c", "d", "e"];
      arr.splice(1, 3, "aa"); // ["a", "aa", "e"]
      console.log(addArr); // ["b", "c", "d"]
    </code>
  </pre>

## 배열의 일부 요소 가져오기
* slice  
  * 문법: array.slice(start[, end])  
  * 배열열의 start부터 end 전까지 배열의 부분 새로운 문자열을 반환한다.  
  * splice와 다르게 원본 배열은 바뀌지 않는다. (얕은 복사본을 반환)
  * start
    * undefined인 경우에는, 0번 인덱스부터 slice 합니다.
    * 배열의 길이보다 큰 경우에는, 빈 배열을 반환합니다.
    * 음수인 경우 배열의 끝에서부터 음수의 절대값만큼 거꾸로 계산된다. 음수값의 절대값이 배열의 길이 보다 큰 경우 0으로 설정된다.
  * end
    * 음수인 경우 배열의 끝에서부터의 길이를 나타냅니다. 예를들어 slice(2,-1) 는 세번째부터 끝에서 두번째 요소까지 추출합니다.
    * 생략하거나 값이 array.length보다 크면 start부터 모든 요소를 추출합니다.
  <pre>
    <code>
      var arr = ["a", "b", "c", "d", "e"];
      arr.slice(1, 3); // ["b", "c"]
      arr.slice(-2, 3); // ["d", "e"]
      arr.slice(3); // ["d", "e"]
      arr.slice(); // ["a", "b", "c", "d", "e"]
      arr.slice(7); // []
      console.log(arr); // ["a", "b", "c", "d", "e"]
    </code>
  </pre>

## 배열의 순서 반전
* reverse 
  * 문법: array.reverse()  
  * 배열의 순서를 반전하는 메서드이다.
  * 원본 배열을 반전하며 그 참조를 반환한다.
  <pre>
    <code>
      var arr1 = ["a", "b", "c", "d"];
      var arr2 = arr.reverse();
      console.log(arr1); // ["d", "c", "b", "a"]
      console.log(arr2); // ["d", "c", "b", "a"]
    </code>
  </pre>

## 배열의 순서 정렬
* sort 
  * 문법: array.sort([compareFunction])  
  * 배열의 순서를 **문자열의 유니코드 코드 포인트**를 따라 정렬하는 메서드이다.
    * compareFunction이 제공되지 않으면 요소를 문자열로 변환하고 오름차순으로 정렬된다.
    * 문자에서 대소문자를 구분하여 정렬된다. (대문자가 오름차순에서 우선이다.)
    * 숫자 또한 문자로 인식하기 때문에 숫자의 첫번째 자리를 기준으로 정렬된다. (음수일 경우 음수 오름차순에서 우선되고, 음수의 첫번째 자리를 기준으로 정렬된다.)
  * 원본 배열을 정렬하며 그 참조를 반환한다.
  <pre>
    <code>
      var strArr1 = ["b", "e", "a", "d"];
      console.log(strArr1.sort()); // ["a", "b", "c", "d"]

      var strArr2 = ["a", "A", "B", "b"]
      console.log(strArr2.sort()); // ["A", "B", "a", "b"]

      var numArr1 = [2, 10, 5, 2];
      console.log(numArr1.sort()); // [2, 2, 5, 10]

      var numArr2 = [200, 10, 3, -3, ,-300, -100];
      console.log(numArr2.sort()); // [-100, -3, -300, 10, 200, 3]
    </code>
  </pre>

  원하는대로 정렬한 결과를 얻기 위해서는 compareFuction을 넣어주어야한다.
  <pre>
    <code>
      // 숫자 오름차순으로 정렬
      numArr.sort(function compareNumbers(a, b) {
        return a - b;
      });

      // 숫자 내림차순으로 정렬
      numArr.sort(function compareNumbers(a, b) {
        return b - a;
      });

      // 숫자 또는 문자 정렬에 경우를 다르게 줄 경우
      numNum.sort(function (a, b) {
        if (a > b) {
          // b가 더 클 경우(오름차순)
        }
        if (a < b) {
          // a가 더 클 경우(내림차순)
        }
        // a랑 b가 같을 경우
        return 0;
      });

      strNum.sort(function (a, b) {
        var nameA = a.toUpperCase(); // 대소문자 구분을 없애 정렬
        var nameB = b.toUpperCase(); // 대소문자 구분을 없애 정렬

        if (nameA > nameB) {
          // a가 먼저 올 경우(오름차순)
        }
        if (nameA < nameB) {
          // b가 먼저 올 경우(오름차순)
        }
        // a랑 b가 같을 경우
        return 0;
      });
    </code>
  </pre>

## Reference
* []
  * 문법: array[index] = element  
  * 대괄호를 이용하여 배열의 index 위치에 element를 추가하거나 수정할 수 있다.  
  <pre>
    <code>
      var arr = ["a", "b", "c"];
      arr[5] = "f";
      console.log(arr); // ["a", "b", "c", empty x 2, "f"]
      console.log(arr[3]); // undefined
      arr[3] = "d";
      console.log(arr); // ["a", "b", "c", "d", empty, "f"]
      console.log(arr[3]); // "d"
    </code>
  </pre>