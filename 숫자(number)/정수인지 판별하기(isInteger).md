# 정수인지 판별하기(isInteger)
## isInteger
  * 문법: Number.isInteger(value)
  * value가 정수인지 아닌지 판별하여 boolean값으로 반환한다.
  * value가 NaN이나 Infinity인 경우 false를 반환한다.
  * **IE에선 작동하지 않는다.**
  <pre>
    <code>
    Number.isInteger(10); // true
    Number.isInteger(0); // true
    Number.isInteger(-10); // true
    Number.isInteger(9999999999); // true
    Number.isInteger(NaN); // false
    Number.isInteger(Infinity); // false
    Number.isInteger('ab'); // false
    Number.isInteger(true); // false
    </code>
  </pre>