# 배열의 요소 위치 가져오기
## indexOf
* 문법: arr.indexOf(searchElement[, fromIndex])
* 배열에서 searchElement를 검색하여 첫 번째로 발견한 인덱스를 반환하고, 존재하지 않으면 -1을 반환한다.
* fromIndex를 지정하면 검색을 시작할 위치를 정할 수 있다.
<pre>
  <code>
    var array = ["a", "b", "c", "c", "b", "a"];
    array.indexOf("b"); // 1
    array.indexOf("e"); // -1
    array.indexOf("a", 2); // 5
    array.indexOf("c", -2); // -1
    array.indexOf("b", -7); // -1

    // 요소의 모든 항목 찾기
    var indices = [];
    var array = ["a", "b", "a", "c", "a", "d"];
    var element = "a";
    var idx = array.indexOf(element);
    while (idx != -1) {
      indices.push(idx);
      idx = array.indexOf(element, idx + 1);
    }
    console.log(indices); // [0, 2, 4]
  </code>
</pre>

## lastIndexOf
* 문법: arr.lastIndexOf(searchElement[, fromIndex])
* 배열의 끝에서 **역순으로** searchElement를 검색하여 첫 번째로 발견한 인덱스를 반환하고, 존재하지 않으면 -1을 반환한다.
* fromIndex를 지정하면 역으로 검색을 시작할 위치를 정할 수 있다.
<pre>
  <code>
    var array = ["a", "b", "c", "c", "b", "a"];
    array.lastIndexOf("b"); // 4
    array.lastIndexOf("e"); // -1
    array.lastIndexOf("a", 2); // 0
    array.lastIndexOf("c", -2); // 3
    array.lastIndexOf("b", -7); // -1

    // 요소의 모든 항목 찾기
    var indices = [];
    var array = ["a", "b", "a", "c", "a", "d"];
    var element = "a";
    var idx = array.lastIndexOf(element);
    while (idx != -1) {
      indices.push(idx);
      idx = (idx > 0 ? array.lastIndexOf(element, idx - 1) : -1);
    }

    console.log(indices); // [4, 2, 0]
  </code>
</pre>
  
## []
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