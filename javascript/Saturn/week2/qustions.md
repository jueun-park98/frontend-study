1. 아래 코드의 실행 컨텍스트 스택 순서는 어떻게 될까?

```jsx
const x = 1;

function foo() {
	const y = 2;

	function bar() {
		const z = 3;
		console.log(x+y+z);
	}
	bar();

foo();
```

2. 식별자와 식별자에 바인딩된 값, 그리고 상위 스코프에 대한 참조를 기록하는 자료구조로 실행 컨텍스트를 구성하는 컴포넌트는? 스코프와 식별자를 관리하는 역할을 한다.

3. 외부 렉시컬 환경에 대한 참조는 **\_**를 가리킨다.
