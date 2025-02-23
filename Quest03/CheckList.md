## Checklist
### 자바스크립트는 버전별로 어떻게 변화하고 발전해 왔을까요?
#### ES1(1997), ES2(1998),ES3(1999)
* ECMA 초기 버전으로 1년에 한 번씩 업데이트되었으며 ES4의 경우 정치적인 이유로 폐기되었다.(ES4를 개발할 때 ES3.1을 작성하는 그룹과 ES4를 작성하는 그룹이 나뉘었고 그 사이에 갈등이 생겨 결국 ES3.1이 추후 ES5가 된다.)
* 대부분의 브라우저에서 지원
* 클로져
* ES3에서 try/catch 문법 추가

#### ES5(2009)
* 배열 forEach, map, filter, reduce, some 메소드 추가
* 객체 Object에 대한 getter/setter 추가
* bind 메소드 추가
* JSON 추가
* strict moce 추가
* es5-shim 사용 시 하위 버전에서 특정 기능 지원

#### ES6(2015)
* let, const 키워드 추가
* arrow 문법 지원
* iterator, generator 추가
* module import, export 추가
* callback hell을 해결할 Promise 추가
* MS에서도 최대한 ECMAScript를 따르는 브라우저 IE Edge 발표

#### ES7(2016)
* 제곱연산자(**) 추가
* Array.includes 추가

#### ES7(2016)
* async/await 추가
* 이후 나오는 표준은 ES.Next라고 한다.
<br><br>

### 자바스크립트의 버전들을 가리키는 ES5, ES6, ES2016, ES2017 등은 무엇을 이야기할까요?
ES는 Ecma Script의 약자다. Ecma Script 2016 은 2016년도에 정한 ECMAScript 라는 뜻이다. 년도가 아닌 6, 7, 8 과 같이 붙은 것은 버전 단위로 명칭을 붙이면서 파생된 버전형 명칭이다.
<br><br>

### 자바스크립트의 표준은 어떻게 제정될까요?
Ecma International이라는 국제 표준화 기구에서 ECMA-262 기술 규격에 따라 표준화된 스크립트 프로그래밍 언어를 정의하고 있으며, JavsScript는 ECMAScript사양을 준수하고 있다.
<br><br>

### 자바스크립트의 문법은 다른 언어들과 비교해 어떤 특징이 있을까요?
1. 인터프리터 언어: 기존에는 자바스크립트가 인터프리터 언어라는 특성으로 인해 느리다는 편견이 있었지만 사용자의 컴퓨터 성능이 증가하고 브라우저내의 자바스크립트 엔진이 발전함에 따라 성능이 좋아졌다.
2. 동적 타입 언어: Java나 C++등의 언어처럼 변수의 타입이 선언과 동시에 정해지는 정적 타입 언어가 아닌 실행되는 도중에 타입이 동적으로 바뀔 수 있는 동적 타입 언어다.
3. 함수 자체가 자료형이고 객체: 자바스크립트에서는 함수 자체가 객체이고 자료형이며, 따라서 다른 함수를 호출할때 함수를 인자로 넘길수도 있고 함수자체를 리턴할 수 있다. 이런 함수를 일급 함수라고 하며, 따라서 자바스크립트는 일급함수 언어라고 한다.
4. 객체지향이면서도 함수지향: 자바스크립트는 객체지향적인 코딩과 함수지향적 코딩이 가능한 멀티 패러다임 언어이다.
5. 함수가 스코프를 정의한다: 다른 언어들은 if문이나 for문 안에서 사용되는 변수또한 지역변수로 사용되지만 자바스크립트는 함수 범위에 따라 변수의 스코프가 정의된다. 물론 최신버전의 자바스크립트는 함수 범위뿐 아니라 몇가지 문법을 통해 스코프를 결정할 수 있게 바뀌었으나 아직까지는 기존의 함수를 통해 스코프를 정의하는 방법을 많이 사용한다.
6. 브라우저 조작: 자바스크립트는 태생이 브라우저 엔진 위에서 동작하는 언어이므로 브라우저의 화면(DOM)이나 기능들을 조작할 수 있는 API를 제공한다. 물론 NodeJS는 서버환경이기 때문에 NodeJS에서 사용되는 자바스크립트의 경우에는 브라우저를 조작할 수 있는 API가 없다.
<br><br>

### 자바스크립트에서 반복문을 돌리는 방법은 어떤 것들이 있을까요?
1. for: 고전적인 for문
2. for in: 객체의 프로퍼티 키 열거 전용
3. for of: 이터러블 순회 전용
4. forEach(): 배열 순회 전용 메서드
5. while: 고전적인 while문
6. do while: 고전적인 do...while문
7. Object 객체 메서드: 객체 순회 전용
8. Array.prototye 메서드: 배열 전용
<br><br>

### 자바스크립트를 통해 DOM 객체에 CSS Class를 주거나 없애려면 어떻게 해야 하나요?
```javascript
var element = document.getElementById('element');

/*클래스 추가*/
element.classList.add('className');

/*클래스 삭제*/
element.classList.remove('className');
```
<br><br>

#### IE9나 그 이전의 옛날 브라우저들에서는 어떻게 해야 하나요?
```javascript
element.className = className;  
```
<br><br>


### 자바스크립트의 변수가 유효한 범위는 어떻게 결정되나요?
자바스크립트에서 변수는 유효 범위에 따라 다음과 같이 구분된다.
1. 지역 변수(local variable): 함수 내에서 선언된 변수를 가리킨다. 지역 변수는 변수가 선언된 함수 내에서만 유효하며, 함수가 종료되면 메모리에서 사라진다.
2. 전역 변수(global variable): 함수의 외부에서 선언된 변수를 가리킨다. 전역 변수는 프로그램의 어느 영역에서나 접근할 수 있으며, 웹 페이지가 닫혀야만 메모리에서 사라진다.
<br><br>

### `var`과 `let`으로 변수를 정의하는 방법들은 어떻게 다르게 동작하나요?
1. var는 함수 레벨 스코프이고 let는 블럭 레벨 스코프다.
2. var로 선언한 변수는 선언 전에 사용해도 에러가 나지 않지만 let는 에러가 발생한다.
3. var는 이미 선언되어있는 이름과 같은 이름으로 변수를 또 선언해도 에러가 나지 않지만 let는 이미 존재하는 변수와 같은 이름의 변수를 또 선언하면 에러가 난다.
<br><br>

### 자바스크립트의 익명 함수는 무엇인가요?
익명 함수(anonymous function)는 변수에 함수의 코드를 저장하는 대신 함수명을 사용하지 않는다. 대신 변수명을 마치 함수명처럼 사용해서 함수를 호출하거나 변수값을 이동시키는데 사용할 수 있다.
  ```
  var 변수명 = function( 매개변수 )
  {
    실행문;
  };
  ```
<br><br>

 ### 자바스크립트의 Arrow function은 무엇일까요?
Arrow function은 function 키워드 대신 화살표(=>)를 사용하여 보다 간략한 방법으로 함수를 선언하는 방법. Arrow Function은 일반 함수와 달리 this와 arguments가 없다.
    `let func = (arg1, arg2, ...argN) => expression`