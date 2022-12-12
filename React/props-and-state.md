# props란?
props는 컴포넌트의 <strong>속성(property)</strong>을 뜻한다.


## props의 특징 
<ol>
<li>외부로부터 전달받은 값이다.</li>
<li>부모 컴포넌트(상위 컴포넌트)로부터 전달받은 값이다.</li>
<li><u>객체</u> 형태이다.</li>
props로 어떤 타입의 값도 넣어 전달할 수 있도록 하기 위함이다.
<li>읽기 전용 객체이다.</li>
props는 외부로부터 전달받아 변하지 않아야 하는 값이기 때문이다.
</ol>

## props 사용법

<ol>
<li>부모 컴포넌트와 자식 컴포넌트 선언</li>
<li>부모 컴포넌트 안에 자식 컴포넌트 작성</li>
<li>부모 내부의 자식에게 props(속성 및 할당값) 전달</li>
<li>자식 컴포넌트에서 props 받기</li>
<li>자식 컴포넌트에서 dot notation으로 props 렌더링</li>
</ol>

```
// 부모와 자식 컴포넌트 선언하고 자식 컴포넌트를 부모 내부에 위치시킨다.
function Parent() {
  return (
    <div className="parent">
      <h1>I'm the parent</h1>
      // 자식 컴포넌트에 props를 전달한다.
      <Child text={"I'm a child"}/> 
    </div>
  );
};

// 자식 컴포넌트에서 props를 받는다.
function Child(props) {
  return (
    // 자식 컴포넌트에서 props를 렌더링한다.
    <div className="child">{props.text}</div> 
  );
};
```

# state란?
state는 상태라는 뜻으로, 컴포넌트 내에서 변할 수 있는 값을 의미한다.<br>
예를 들어 장바구니 컴포넌트에서 구매할 물건과 구매하지 않을 물건을 체크 박스로 구분 하려고 할때,<br>
체크 박스의 상태는 checked와 unchecked로 나누어질 수 있다.

## useState
React에서는 useState라는 hook을 이용하여 state를 다룬다.

### *useState 사용법
1. `import` 키워드로 useState 불러오기
    ```
    import { useState } from "react";
    ```
2. useState를 컴포넌트 안에서 호출하기<br>
이는 "state"라는 변수를 선언하는 것과 같다.<br>
state 변수는 React에 의해 함수가 끝나도 사라지지 않는다.
    ```
    function CheckboxExample() {
    const [isChecked, setIsChecked] = useState(false);
    }
    ```
    ```
    const [state 저장 변수, state 갱신 함수] = useState(상태 초기 값);
    ```
    - isChecked : state를 저장하는 변수
    - setIsChecked : state isChecked 를 변경하는 함수
    - useState : state hook
    - false : state 초깃값  
3. jsx 엘리먼트 내부에서 state 변수를 직접 불러서 사용한다.

    ```
    // 체크 컴포넌트 예시
    function CheckboxExample() {
      const [isChecked, setIsChecked] = useState(false);

      const handleChecked = (event) => {
        setIsChecked(event.target.checked);
      };

      return (
        <div className="App">
          <input type="checkbox" checked={isChecked} onChange={handleChecked} />
          <span>{isChecked ? "Checked!!" : "Unchecked"}</span>
        </div>
      );
    };
    ```
### *controlled component
React가 state를 통제할 수 있는 컴포넌트를 말한다.

# 단방향 데이터 흐름




