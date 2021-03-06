# ES6 문법

## 1. const, let
- var는 함수 스코프를 가진다.
- const와 let은 블록 스코프를 가진다.

## 2. 템플릿 문자열
- 문자열을 백틱(`)으로 감싼다.
- 문자열 안에 변수를 넣을 수 있다.
  - ${변수} 형식으로 사용한다.

## 3. 객체 리터럴
- 객체의 메서드에 함수를 연결할 때 콜론(:)과 function을 붙이지 않아도 된다.
- sayNode: sayNode처럼 속성명과 변수명이 동일한 경우에는 한 번만 써도 된다.
  - ex) { name: name, age: age } ==> { name, age }
- 객체 리터럴 안에서 동적 속성을 선언할 수 있다.

## 4. 화살표 함수
- 함수 내부에 return문밖에 없는 경우에 화살표 함수를 사용하여 줄일 수 있다.
  - ex) const add = (x, y) => x + y;
- 화살표 함수를 사용하여 상위 스코프의 this를 그대로 사용할 수 있다.

## 5. 구조분해 할당
- 구조분해 할당을 사용하면 객체와 배열로부터 속성이나 요소를 쉽게 꺼낼 수 있다.
  - ex) const { getCandy, status: { count } } = candyMachine;
  - candyMachine 객체 안의 속성을 찾아서 변수와 매칭한다.
  - count처럼 여러 단계 안의 속성도 찾을 수 있다.
- 배열을 구조분해 할당할 수 있다.
  - ex)
    - const array = ['nodejs', {}, 10, true]; <br> const [node, obj, , bool] = array;

## 6. 클래스
- 생성자 함수는 constructor 키워드를 사용한다.
- extends 키워드로 상속을 한다.
- 프로토타입 기반으로 동작한다.

## 7. 프로미스
- 이벤트 리스너를 사용할 때 콜백 대신 프로미스를 사용한다.
- new promise로 프로미스를 생성한다.
- promise 변수에 then과 catch 메서드를 붙일 수 있다.
  - 콜백 함수 호출이 성공하면 then이 실행된다.
  - 실패(오류)하면 catch가 실행된다.
  - finally는 then과 catch가 끝나고 무조건 실행되는 메서드이다.
- 실행은 바로 하되 결과 값은 then이나 catch가 실행되고 받는다.
- 콜백 함수를 여러 번 중첩하는 대신에 then을 여러 번 이어 붙일 수 있다.
  - 마지막 catch에서 에러를 한 번에 처리할 수 있다.
  - then을 여러 번 이어 붙이는 대신에 promise.all을 활용해서 프로미스 여러 개를 한번에 실행할 수 있다.

## 8. async/await
- 프로미스를 사용한 코드를 한 번 더 깔끔하게 줄여준다.
- 함수 선언부를 일반 함수 대신 async function으로 교체한 후, 프로미스 앞에 await을 붙인다.
  - 프로미스가 resolve될 때까지 기대린 뒤 다음 로직으로 넘어간다.
- try/catch문으로 로직을 감쌀 수 있다.
- 화살표 함수와 같이 사용할 수 있다.