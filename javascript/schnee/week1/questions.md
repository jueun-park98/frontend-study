## 변수란 무엇인가? 왜 필요한가?
1. 변수에 값을 저장하는 것을 할당이라 하고, 변수에 저장된 값을 읽어 들이는 것을 참조라 합니다.
다음 코드를 읽고 할당을 하는 부분과 참조하는 부분을 모두 찾으세요.

```
const array1 = ['a', 'b', 'c'];
const array2 = ['d', 'e', 'f'];
const array3 = array1.concat(array2);

console.log(array3);
```

2. 다음 코드를 실행하면 10, 20, 30라는 number 값이 메모리에 생성됩니다. 운영체제는 10, 20이 저장된 메모리에 접근이 가능하지만, 30에는 접근이 불가능합니다. 그 이유를 설명해주세요.
```
const result = 10 + 20;
```

### 변수 선언의 실행 시점과 변수 호이스팅
  다음 코드를 에러가 발생할 수 있게 수정해주세요. 그리고 다음 코드가 에러가 나지 않는 이유를 설명하는 단어를 적어주세요.
```
console.log(score);

var score;
```

### 데이터 타입의 필요성
  65라는 number 값을 메모리에 저장하려고 합니다. 만약 number라는 타입이 없으면 발생할 수 있는 상황을 설명하세요.



### 데이터 타입
  다음 중 객체가 아닌 것을 모두 고르세요.
1) `5`
2) `'schnee'`
3) `{ width: 100 }`
4) `[1, 2, 3]`
5) `(number) => number++;`
6) `Symbol("noodle");`
7) `function sayHi() { console.log("hi") }`
