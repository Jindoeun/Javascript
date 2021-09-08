# Type 변환하기 (number, string)  
## 숫자로 변환하기
* Number  
  * 문법: Number(string)  
  * 숫자로 변환시켜주는 함수이다.
  * 숫자와 문자가 혼용될 경우, 숫자가 앞에 있을 경우만 숫자만 추출하여 변환해 준다.
  <pre>
    <code>
      var str1 = "2입니다."
      var str2 = "이것은 2입니다."
      console.log(typeof(str)); //string
      
      str1 = Number(str1);
      console.log(str1, typeof(str1)); //2 number

      str2 = Number(str2);
      console.log(str2, typeof(str2)); //NaN number
    </code>
  </pre>

* parseInt    
  * 문법: parseInt(string[, radix])  
  * **정수**로 변환시켜주는 함수이다.  
  * radix는 기수로 parse할 때 기준이 되는 진수이며, 정수로 변환할 경우만 지정할 수 있다. 2 ~ 36진수까지를 정의할 수 있고, 따로 radix를 지정하지 않을 경우 10진수로 변환한다.

* parseFloat     
  * 문법: parseFloat(string)  
  * **실수**로 변환시켜주는 함수이다.  

  <pre>
    <code>
      var str = "3.12";
      console.log(typeof(str)); //string
      
      var integer = parseInt(str);
      console.log(integer, typeof(integer)); // 3 number
      
      var float = parseFloat(str);
      console.log(float, typeof(float)); // 3.12 number
    </code>
  </pre>


## 문자로 변환하기
* String  
  * 문법: String(number)  
  * 문자열로 변환시켜주는 함수이다.
  
* toString  
  * 문법: str.toString([radix]) 
  * 문자열로 변환시켜주는 메서드이다.

  <pre>
    <code>
      var num = 3.12;
      console.log(typeof(num)); //number
      
      var str1 = String(num);
      console.log(str1, typeof(str1)); // "3.12" string
      
      var str2 = num.toString();
      console.log(str2, typeof(str2)); // "3.12" string
    </code>
  </pre>


## Reference
<pre>
  <code>
    // number -> string
    var num = 2;
    num += "";
    console.log(num, typeof(num)); // "2" string

    // string -> number
    str = "2"
    str *= 1;
    console.log(str, typeof(str)); // 2 number
  </code>
</pre>
