# Component 란?
- React로 만들어지는 앱의 최소 단위
- 하나의 기능 구현을 위한 코드 묶음
- 재사용성, 유지보수 측면에서 편리하도록 만들어준다.
- 컴포넌트의 이름은 대문자로 시작한다.
- props를 통해 부모 컴포넌트는 자식 컴포넌트에게 속성 및 값을 전달해줄 수 있다.

# Component의 종류
## Class Component
    ```
    class Child extends React.Component {
		render() {
			return <h1>Hello, World</h1>;
		}
	}
    ```
    
- 클래스 컴포넌트는 React.Component 클래스를 상속받아 구성된다.
- 컴포넌트는 jsx를 반환해야 하는데, class에서는 return문을 사용할 수 없으므로,<br>`render()`함수를 사용하여 리턴한다.


## Function Component
    ```
    function Child(props) {
            return <h1>Hello, World</h1>;
        }

    ```

- 함수 컴포넌트는 Javascript의 함수와 같이 매개변수를 받아서 (props를 받는다.) 렌더링할 수 있다.
- 함수 컴포넌트에서는 return문을 이용하여 jsx를 반환한다.