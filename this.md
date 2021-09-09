# this
this를 알려면 우선 context가 무엇인지 알아야한다.  
간단하게 context란 **this가 가리키는 객체**라고 할 수 있다.

* 기본 바인딩 (전역객체)
  <pre>
    <code>
    console.log(this); // window
    
    function func() {
      console.log(this); // window
    }
    </code>
  </pre>
  해당 코드를 출력해보면 window 라고 뜨는 것을 알 수 있다.
  this는 기본적으로 전역 스코프와 전역 스코프에서 생성된 함수에서는 전역 객체(window)를 context로 가지고 있다.
  <br><br>
  또한 this를 이해하기 위해서 변수를 선언하는 것은 전역 객체에 property를 등록하는 것과 같다는 것을 알아야한다.  
  무슨 말이냐하면 var a = 1은 window.a = 1 과 같다는 말이다. 이 말을 생각하면서 아래의 코드를 보자.
  <pre>
    <code>
    var a = 10;
    console.loa(this.a); // 10
    
    function getThis() {
      this.variable1 = "ab"; // 전역 변수로 선언해주는 것과 같다.
      console.log(this); // window
    }
    
    console.log(this.variable1); // undefined
    console.log(this.variable2); // undefined
    
    this.variable2 = "cd";
    
    console.log(this.variable1); // undefined
    console.log(this.variable2); // cd
    
    getThis();
    
    console.log(this.variable1); // ab
    console.log(this.variable2); // cd
    </code>
  </pre>
  getThis가 실행되면서 전연 객체에 variable1: "ab"를 등록해주었으므로 마지막 console에 this.variable1이 "ab"로 찍힐 수 있는 것이다.
  <br>
  <br>

* 암시적 바인딩
  객체에서 선언된 함수에서 this를 호출하면 어떻게 될까?  
  어떤 객체를 통해 함수가 호출되면 그 객체가 this의 context가 된다.
  <pre>
    <code>
    var a = 10;
    
    function outFunc() {
      console.log(this.a);
    }
    
    var obj = {
      a: 20,
      func1: outFunc,
      func2: function() {
        console.log(this.a);
      }
    };
    
    obj.func1(); // 20
    obj.func2(); // 20
    
    this.variable1 = obj.func1; // => window.variable1 = obj.func1
    this.variable2 = obj.func2; // => window.variable2 = obj.func2
    this.variable1(); // 10
    this.variable2(); // 10
    </code>
  </pre>
  outFunc이 생성된 곳은 전역 스코프이나 호출은 객체인 obj의 property로써 호출되었기 때문에 obj.func1()과 obj.func2()에서 this는 obj를 가르키게 된다. 그러나 this.variable1()과 this.variable2()에서는 전역 스코프에서 this인 window의 property로 등록시킨 후 호출되었기 때문에 this는 window를 가르키게 된다.
  