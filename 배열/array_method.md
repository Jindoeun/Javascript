# 배열(array) 메서드
## 배열의 요소 추가
* push
  * 문법: arr.push(element1[, ...[, elementN]]))  
  * 배열의 맨끝에 element를 추가하는 메서드이다.
  * 여러개도 가능하다.
  * 추가한 뒤, 배열의 길이를 반환한다.  
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
  * 문법: arr.unshift(element1[, ...[, elementN]]))  
  * 배열의 맨앞에 element를 추가하는 메서드이다.
  * 여러개도 가능하다.
  * 추가한 뒤, 배열의 길이를 반환한다.  
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
  * 문법: arr.pop()  
  * 배열의 맨끝에 요소를 제거하는 메서드이다.
  * 제거한 뒤, 제거된 요소를 반환한다.  
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
  * 문법: arr.shift()  
  * 배열의 맨앞에 요소를 제거하는 메서드이다.
  * 제거한 뒤, 제거된 요소를 반환한다. 
  * 빈 배열에 shift를 호출하면 undefined를 반환한다.   
  <pre>
    <code>
      var arr = ["a", "b", "c", "d", "e"];
      var element = arr.shift();
      console.log(element); // "a"
      console.log(arr); // ["b", "c", "d", "e"]
    </code>
  </pre>
* splice
  * 문법: arr.splice()  
  * 배열의 맨앞에 요소를 제거하는 메서드이다.
  * 제거한 뒤, 제거된 요소를 반환한다. 
  * 빈 배열에 shift를 호출하면 undefined를 반환한다.   
  <pre>
    <code>
      var arr = ["a", "b", "c", "d", "e"];
      arr.splice(1, 3); // splice(start, count)
      console.log(arr); // ["a", "e"]
    </code>
  </pre>

## 배열의 순서 반전
* reverse 
  * 문법: arr.reverse()  
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
  * 문법: arr.sort([compareFunction])  
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
  * 문법: arr[index] = element  
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