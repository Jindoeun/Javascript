# 배열의 순서 정렬
## sort 
* 문법: array.sort([compareFunction])  
* 배열의 순서를 **문자열의 유니코드 코드 포인트**를 따라 정렬하는 메서드이다.
  * compareFunction이 제공되지 않으면 요소를 문자열로 변환하고 오름차순으로 정렬된다.
  * 문자에서 대소문자를 구분하여 정렬된다. (대문자가 오름차순에서 우선이다.)
  * 숫자 또한 문자로 인식하기 때문에 숫자의 첫번째 자리를 기준으로 정렬된다. (음수일 경우 음수 오름차순에서 우선되고, 음수의 첫번째 자리를 기준으로 정렬된다.)
* 원본 배열을 정렬하며 그 참조를 반환한다.
<pre>
  <code>
    var strArr1 = ["b", "e", "a", "d"];
    strArr1.sort(); // ["a", "b", "c", "d"]
    console.log(strArr1); // ["a", "b", "c", "d"]

    var strArr2 = ["a", "A", "B", "b"]
    strArr2.sort(); // ["A", "B", "a", "b"]
    console.log(strArr2); // ["A", "B", "a", "b"]

    var numArr1 = [2, 10, 5, 2];
    numArr1.sort(); // [2, 2, 5, 10]
    console.log(numArr1); // [2, 2, 5, 10]

    var numArr2 = [200, 10, 3, -3, ,-300, -100];
    numArr2.sort(); // [-100, -3, -300, 10, 200, 3]
    console.log(numArr2); // [-100, -3, -300, 10, 200, 3]
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