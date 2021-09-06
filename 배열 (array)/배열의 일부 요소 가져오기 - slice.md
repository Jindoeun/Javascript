# 배열의 일부 요소 가져오기
## slice  
* 문법: array.slice(start[, end])  
* 배열열의 start부터 end 전까지 배열의 부분 새로운 문자열을 반환해주는 메서드이다.  
* splice와 다르게 원본 배열은 바뀌지 않는다. (얕은 복사본을 반환)
* start
  * undefined인 경우에는, 0번 인덱스부터 slice 한다.
  * 배열의 길이보다 큰 경우에는, 빈 배열을 반환한다.
  * 음수인 경우 배열의 끝에서부터 음수의 절대값만큼 거꾸로 계산된다. 음수값의 절대값이 배열의 길이 보다 큰 경우 0으로 설정된다.
* end
  * 음수인 경우 배열의 끝에서부터 음수의 절대값만큼 거꾸로 계산된다.
  * 생략하거나 값이 array.length보다 크면 start부터 모든 요소를 추출한다.
<pre>
  <code>
    var arr = ["a", "b", "c", "d", "e"];
    arr.slice(1, 3); // ["b", "c"]
    arr.slice(-2, 3); // ["d", "e"]
    arr.slice(-2, -1); // ["d"]
    arr.slice(3); // ["d", "e"]
    arr.slice(); // ["a", "b", "c", "d", "e"]
    arr.slice(7); // []
    console.log(arr); // ["a", "b", "c", "d", "e"]
  </code>
</pre>