### 1. textContent를 사용하여 DOM 요소의 텍스트를 변경할 때 기존의 하위 노드들은 어떻게 되는가?

```javascript
// 예시 코드
const element = document.createElement("div");
element.innerHTML = "<span>텍스트</span>";
console.log(element.textContent); // "텍스트"

element.textContent = "새로운 텍스트";
console.log(element.innerHTML); // "새로운 텍스트"
```

<details>
  <summary>정답</summary>
  textContent를 사용하면 해당 노드의 모든 하위 노드가 제거되고 새로운 텍스트 노드로 대체된다. <br>
  따라서 기존의 DOM 구조는 사라지고 텍스트만 남는다.
</details>

### 2. innerHTML을 사용하여 DOM 요소의 내용을 변경할 때 주의해야 할 점은 무엇인가?

<details>
  <summary>정답</summary>
  innerHTML을 사용하면 문자열로 전달된 HTML을 파싱하여 DOM에 반영한다. <br>
  따라서 악성 스크립트가 포함된 문자열을 innerHTML로 설정하면 보안 문제가 발생할 수 있다. (XSS) <br>
  사용자 입력을 innerHTML에 직접 설정하는 것은 피해야 하며, 반드시 신뢰할 수 있는 데이터만 사용해야 한다.

```javascript
// 예시 코드
const element = document.createElement("div");
element.innerHTML = "<script>console.log('악성 스크립트')</script>";

// DOM에 추가
// document.body.appendChild(element);
```

</details>

### 3. insertBefore 메서드 실행 시 타겟 child node가 없으면?

<details>
  <summary>정답</summary>
  appendChild처럼 맨 뒤에 추가된다.
</details>

### 3. insertBefore 메서드 실행 시 삽입할 노드가 기존에 있던 노드라면?

<details>
  <summary>정답</summary>
  기존 위치에서 새로 삽입할 위치로 이동한다.
</details>

### 4. element의 현재 css 속성을 가져오는법은?

<details>
  <summary>정답</summary>
  window.getComputedStyle을 사용하면 가능하다. 두번째 인수로 :after, :before같은 의사 요소 지정 문자열을 전달 가능하다.
</details>
