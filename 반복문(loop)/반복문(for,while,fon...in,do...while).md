# 반복문
* for
  * 문법
  <pre>
    <code>
      for (초기문; 조건문; 증감문){
        실행문;
      } // 실행문이 한 줄인 경우 중괄호 생략 가능
    </code>
  </pre>  
  * 조건문이 falsy로 판별될 때까지 실행문을 반복한다.
  * for문이 실행되는 순서
    1. 초기화 구문인 초기문이 존재한다면 for문이 실행될 때 제일 처음으로 한번만 실행된다. 이 표현은 보통 변수로 선언되어 0이나 반복문 카운터로 초기 설정이 된다.
    2. 조건문은 조건을 검사한다. 만약 조건문이 truthy라면 실행문으로 넘어가게 되고, 만약 조건문이 falsy라면 그 for문은 여기서 종결된다. 만약 그 조건문이 생략된다면, 그 조건문은 truthy로 추정한다.
    3. 실행문이 실행된다. 많은 문장을 실행할 경우엔, { } 를 써서 문장들을 묶어준다.
    4. 갱신 구문인 증감문이 존재한다면 실행되고, 2번째 단계로 돌아가 falsy가 반환될 때까지 계속 반복 된다.
    <pre>
      <code>
      var i;
      function init () {
        console.log('A');
        i = 0;
      }
      function condition () {
        console.log('B');
        // if(i < 2){
        // 	return true;
        // }
        return i < 2; // 위의 if문과 동일
      }
      function update () {
        console.log('C');
        i++;
      }

      for (init(); condition(); update()) {
      }

      // A > B > C > B > C > B
      </code>
    </pre>
  * 앞의 초기문, 조건문, 증감문은 모두 생략이 가능하다. (반복문 이전의 코드에서 변수를 선언했을 경우나 실행문에서 증감을 할 경우 등등)

* while
  * 문법
  <pre>  
    <code>
      while (조건문;){
          실행문;
      }
    </code>
  </pre>  
  * 조건문이 falsy로 판별될 때까지 실행문을 반복한다.
  <pre>
    <code>
      var i = 0;
      while (i < 3) {
        alert(i); // 0, 1, 2
        i++;
      }
      
      var i = 2;
      while (i >= 0) {
        alert(i); // 2, 1, 0
        i--;
      }
    </code>
  </pre>

* for ... in
  * 문법
  <pre>
    <code>
      for (변수 in 객체){
        실행문;
      }
    </code>
  </pre>
  * 상속된 열거 가능한 속성들을 포함하여 객체에서 문자열로 키가 지정된 모든 열거 가능한 속성에 대해 반복한다.
  <pre>
  <code>
    const object = { a: 1, b: 2, c: 3 };
    for (const property in object) {
      console.log(`${property}: ${object[property]}`);
    }

    // "a: 1"
    // "b: 2"
    // "c: 3"
  </code>
  </pre>

* do ... while
  * 문법
  <pre>
    <code>
      do {
        실행문
      }
      while (조건문);
    </code>
  </pre>
  * 조건문이 falsy로 판별될 때까지 실행문을 반복한다.
  * 단, 구문이 실행된 뒤에 테스트 조건이 평가됨으로 구문은 무조건 한 번은 실행된다.
  <pre>
    <code>
      let result = '';
      let i = 0;
      do {
        i++;
        result += i;
      } while (i < 5);

      console.log(result); // "12345"
    </code>
  </pre>