# 👩‍🏫 week 2 - A

## ▣ 23장: 실행 컨텍스트

### 1️⃣ Q. 자바스크립트 엔진은 소스코드를 2개의 과정(소스코드의 평가, 소스코드의 실행)으로 나누어 처리합니다. 처리되는 과정을 설명해주세요.

소스코드 평가 과정에서는 (실행 컨텍스트)를 생성하고, 변수 함수 등의 (선언문)만 먼저 실행하여 생성된 변수나 함수 식별자를 (키)로 (실행 컨텍스트가 관리하는 스코프)에 등록합니다.

그 과정이 끝나면, (런타임)이 시작되고, 실행에 필요한 정보(변수나 함수의 참조)를 (실행 컨텍스트가 관리하는 스코프)에서 검색하여 취득합니다.

변수 값의 변경 등 소스 코드의 실행 결과는 다시 (실행 컨텍스트가 관리하는 스코프)에 등록됩니다.

### 2️⃣ Q. 그렇다면 실행 컨텍스트는 무엇일까요?

소스코드를 실행하는 데 필요한 환경을 제공하고 코드의 실행 결과를 실제로 관리하는 영역입니다.

<details>
  <summary>🔽 추가 설명 🔽  </summary>

자바스크립트가 코드를 실행할 때 사용하는 환경"이라고 생각할 수 있어요. 자바스크립트 엔진이 코드를 실행하기 위해서는 변수, 함수 등의 정보를 어딘가에 저장하고 관리해야 해요. 실행 컨텍스트는 바로 그런 정보들을 담고 있는 박스와 같은 것이에요.

자바스크립트가 코드를 실행할 때, 이 박스(실행 컨텍스트)를 만들고, 코드에서 사용하는 변수나 함수 같은 것들의 정보를 여기에 넣어요. 이렇게 해서 자바스크립트는 언제 어디서든 필요한 정보를 빠르게 찾아서 사용할 수 있게 됩니다.

실행 컨텍스트는 크게 세 가지 주요 구성 요소를 가지고 있어요:

- 변수 환경(Variable Environment): 현재 컨텍스트 내의 변수, 함수 선언 등의 정보를 저장합니다.
- 외부 환경(Outer Environment): 현재 컨텍스트가 참조하는 외부 코드의 정보를 가리킵니다. 예를 들어, 현재 함수가 다른 함수 안에 있다면, 그 바깥 함수의 실행 컨텍스트를 참조하게 됩니다.
- this 값: 코드가 실행되는 동안 this 키워드가 어떤 객체를 가리키는지 정의합니다.
  코드를 실행할 때, 자바스크립트 엔진은 실행 컨텍스트 스택이라는 것을 사용해요. 이것은 코드의 실행 순서를 관리하는 스택(stack)으로, 자바스크립트는 이 스택에 새로운 실행 컨텍스트를 추가하거나 실행이 끝난 컨텍스트를 제거하면서 코드를 순차적으로 실행합니다.

간단히 말해서, 실행 컨텍스트는 자바스크립트가 코드를 실행하는 데 필요한 모든 정보를 담고 있는 '박스' 같은 것이라고 생각하면 돼요. 이 박스 덕분에 자바스크립트는 어디서 어떻게 코드를 실행해야 할지 알 수 있고, 코드 실행 중에 필요한 모든 정보를 쉽게 접근할 수 있어요.

</details>

### 3️⃣ Q. 스코프와 관련하여 var, let, const 키워드로 선언한 변수를 설명해주세요.

var 키워드로 선언한 변수는 오로지 함수의 코드 블록만 지역 스코프로 인정하는 함수 레벨 스코프를 따릅니다.

하지만 let, const키워드로 선언한 변수는 모든 코드 블록(함수, if문, while문, try/catch문)을 지역 스코프로 인정하는 블록 레벨 스코프를 따릅니다.

<details>
  <summary>🔽 추가 설명 🔽  </summary>

**var**를 사용해서 변수를 선언하면, 그 변수는 함수가 시작하는 곳부터 함수가 끝나는 곳까지 어디서든 사용할 수 있어요.  
만약 함수 바깥에서 var로 변수를 선언하면, 그 변수는 전역 변수가 되어서 프로그램의 어디서든 접근할 수 있죠. 이런 성질 때문에 var는 "함수 레벨 스코프"를 가진다고 해요.  
하지만 이런 특성 때문에 예상치 못한 결과를 낳을 때가 많아요. 예를 들어, 반복문 안에서 var로 변수를 선언하고, 그 변수를 반복문 바깥에서 사용하려고 하면, 반복문의 마지막 값이 저장되어 있어서 혼란을 줄 수 있어요.

**let**과 **const**는 둘 다 "블록 레벨 스코프"를 가지고 있어요. 이 말은, 변수가 선언된 {} 안에서만 사용할 수 있다는 뜻이에요.  
예를 들어, if문이나 for문 같은 코드 블록 안에서 let이나 const로 변수를 선언하면, 그 변수는 해당 블록 안에서만 유효하고, 블록 밖에서는 접근할 수 없어요.  
이런 특성 덕분에 코드를 더 예측 가능하고, 관리하기 쉬워져요.

간단히 말해, var는 예전 방식이고, 변수가 넓은 범위에서 살아있어서 때때로 혼란을 줄 수 있어요.  
let과 const는 더 엄격한 규칙을 가지고 있어서 코드를 더 안전하고 예측 가능하게 만들어줍니다!

</details>