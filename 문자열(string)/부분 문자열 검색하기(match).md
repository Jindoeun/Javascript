# 부분 문자열 검색하기
## match
* 문법: str.match(searchValue)
* 문자열에서 **정규식**인 searchValue가 있는지 탐색하여 일치하는 경우 일치하는 문자열을 첫 번째 요소로 포함하는 Array를 반환한다.
* 일치하는 값이 없으면 null을 반환한다.
* searchValue가 string이나 number이면, new RegExp(obj)를 사용하여 자동으로 정규식으로 변환된다. 만약 searchValue가 플러스 기호와 이어지는 숫자형이라면, RegExp() 매서드는 플러스 기호를 무시한다. 
<pre>
  <code>
  var str = "red is impressive.";

  str.match("red"); // "red"가 포함된 배열
  if (str.match("red") === "red") {
    console.log("Okay");
  } // "Okay"


  var str1 = "NaN means not a number. Infinity contains -Infinity and +Infinity in JavaScript.",
      str2 = "My grandfather is 65 years old and My grandmother is 63 years old.",
      str3 = "The contract was declared null and void.";

  str1.match("number"); // "number"는 문자열이므로 "number"이 포함된 배열
  str1.match(NaN); // NaN은 숫자형이므로 "NaN"이 포함된 배열
  str1.match(Infinity); // Infinity는 숫자형이므로 "Infinity"가 포함된 배열
  str1.match(+Infinity); // "Infinity"가 포함된 배열
  str1.match(-Infinity); // "-Infinity"가 포함된 배열
  str2.match(65); // "65"가 포함된 배열
  str2.match(+65); // 플러스 기호가 붙은 숫자형. "65"가 포함된 배열
  str3.match(null); // "null"이 포함된 배열
  </code>
</pre>