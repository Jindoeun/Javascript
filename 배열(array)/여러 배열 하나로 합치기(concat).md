# 문자열을 배열로 변환
## concat
* 문법: array.concat([value1[, value2[, ...[, valueN]]]])
* array에 value1 ~ valueN을 순서대로 합쳐서 **새로운 배열**을 반환해주는 메서드이다. 기존 배열을 변경하지 않는다.
* value1 ~ valueN: 배열일 경우 해당 배열의 요소가 순서대로 합쳐지고, 배열이 아니면 인수 자체가 합쳐진다. 생략됐을 경우 array 그대로 반환된다.
<pre>
  <code>
    var array1 = ['a', 'b', 'c'];
    var array2 = ['d', 'e', 'f'];
    var array3 = ['g', 'h', 'i'];

    array1.concat(array2); // ["a", "b", "c", "d", "e", "f"]
    array1.concat(array2, array3); // ["a", "b", "c", "d", "e", "f", "g", "h", "i"]
    array1.concat(array2, 'g'); // ["a", "b", "c", "d", "e", "f", "g"]
  </code>
</pre>