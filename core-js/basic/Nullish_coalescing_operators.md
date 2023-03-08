### Nullish coalescing operator '??'

nullish 병합 연산자(nullish coalescing operator) ??를 사용하면 짧은 문법으로 여러 피연산자 중 그 값이 ‘확정되어있는’ 변수를 찾을 수 있다.

a ?? b의 평가 결과가 다음과 같을 떄

- a가 null도 아니고 undefined도 아니면 a
- 그 외의 경우는 b
- `x = (a !== null && a !== undefined) ? a : b;`와 동일
- `??`없이 논리연산자만을 이용하여 코드를 작성하는 경우 코드가 길어진다.

### ??와 ||의 차이

nullist 연산자는 OR 연산자와 상당히 유사해 보인다.

```
let firstName = null;
let lastName = null;
let nickName = "바이올렛";

// null이나 undefined가 아닌 첫 번째 피연산자
alert(firstName ?? lastName ?? nickName ?? "익명의 사용자"); // 바이올렛
```

실제로 위의 예시에서 `??`를 `||`로 바꿔도 그 결과는 동일하다.
그런데 두 연산자 사이에는 중요한 차이점이 있다.

- `||`는 첫 번째 truty한 값을 반환한다.
- `??`는 첫 번째 정의된 값을 반환한다.

`null`과 `undefined`, 숫자 `0`을 구분 지어 다뤄야 할 때 매우 중요한 역할을 한다.

```
let height = 0;

alert(height || 100); // 100
alert(height ?? 100); // 0
```

0이 할당될 수 있는 변수를 사용해 기능을 개발할 땐 `||`보다 `??`가 적합하다.

### `??`의 우선순위

`??`의 연산자 우선순위는 5로 꽤 낮다.

- `=`와 `?`보다는 먼저, 대부분의 연산자보다는 나중에 평가된다.
- 그렇기 떄문에 복잡한 표현식 안에서 `??`를 사용해 값을 하나 선택할 떈 괄호를 추가하는게 좋다.

```
let height = null;
let width = null;

// 괄호를 추가!
let area = (height ?? 100) * (width ?? 50);

alert(area); // 5000
```

```
// 원치 않는 결과
let area = height ?? (100 * width) ?? 50;
```

- `??`는 안정성 관련 이슈 떄문에 `&&`나 `||`와 함께 사용할 수 없다.
  `let x = 1 && 2 ?? 3; // SyntaxError: Unexpected token '??'`

- 위와 같은 제약을 피하기 위해선 괄호를 사용하면 된다.

```
let x = (1 && 2) ?? 3; // 제대로 동작합니다.

alert(x); // 2
```

### 요약

- nullish 병합 연산자 ??를 사용하면 피연산자 중 ‘값이 할당된’ 변수를 빠르게 찾을 수 있다.

- `??`는 변수에 기본값을 할당하는 용도로 사용할 수 있다.

```
// height가 null이나 undefined인 경우, 100을 할당
height = height ?? 100;
```

- `??`의 연산자 우선순위는 대다수의 연산자보다 낮고 `?`와 `=`보다는 높다.

- 괄호없이 `??`를 `||`나 `&&`와 함께 사용하는 것은 금지되있다.
