# 20장 strict mode

# strict mode란?

---

```jsx
function foo() {
	x = 10;
}
foo();

console.log(x); // 10
```

- 이러한 암묵적 전역 선언과 같은 의도하지 않은 오류 발생 가능
    - ES5에 등장한 strict mode

# strict mode의 적용

---

```jsx
'use strict';

//or

function foo() {
	'use strict';
}

// 이렇게 필요한 부분만 즉시실행함수로 감싸서 적용하는것이 바람직
(function () {
	'use strict';

}());
```

# strict mode가 발생시키는 에러

---

- 암묵적 전역
    - 선언하지 않은 변수를 참조시
- 변수, 함수, 매개변수의 삭제
    - delete로 변수, 함수 매개변수를 삭제하면 에러
- 매개변수 이름의 중복
    - 중복된 매개변수 이름을 적용시
- with 문의 사용
    - 전달된 객체를 스코프 체인에 추가
    - 가독성 나빠지니 에러뜸
    

# strict mode 적용에 의한 변화

---

- 일반 함수의 this
    - 일반 함수로 실행 시, this에 undefined 바인딩
    - 원래는 window나 node 반환됨
- arguments 객체
    - 매개변수에 전달된 인수를 재할당하여 변경해도 arguments 객체에는 반영 x
    
    ```jsx
    (function (a) {
    	'use strict';
    	
    	a = 2;
    	
    	console.log(arguments); // {1, callee ...}
    	console.log(a); // 2
    }(1));
    ```