### if와 '?'를 사용한 조건 처리

조건에 따라 다른 행동을 취해야 할 때가 있다.
이럴 땐 if문과 물음표 연산자라고 불리는 조건부 연산자 ? 를 사용한다.

### if문

if(...) 문은 괄호 안에 들어가는 조건을 평가하는데 그 결과가 true이면 코드 블록을 실행한다.

복수의 문을 실행하고 싶다면 중괄호로 코드 블록을 감싸야 한다.

if문을 쓸 때는 조건이 참일 경우 실행되는 구문이 단 한 줄이더라도 중괄호를 사용해 코드를 블록으로 감싸는 것이 코드 가독성이 증가한다.

### else절

if문엔 else 절을 붙일 수 있다.

else뒤에 이어지는 코드 블록은 조건이 거짓일 때 실행된다.

### else if로 복수 조건 처리하기

유사하지만 약간씩 차이가 있는 조건 여러 개를 처리해야 할 때는 else if를 사용할 수 있다.

### 조건부 연산자 '?'

조건에 따라 다른 값을 변수에 할당해줘야 할 때가 있다.

피연산자가 세 개이기 때문에 삼항 연산자라고 부르기도 한다.

자바스크립트에서 피연산자를 3개나 받는 연산자는 조건부 연산자가 유일하다.

### 다중 '?'

물음표 연산자 ?를 여러개 연결하면 복수의 조건을 처리할 수 있다.

(개인적으로 가독성이 떨어진다고 생각..)

### 부적절한 '?'

물음표 ?를 if 대용으로 쓰는 경우가 종종 있는데 가독성이 떨어지기 때문에 좋지 않다.

```
let company = prompt('자바스크립트는 어떤 회사가 만들었을까요?', '');

(company == 'Netscape') ?
   alert('정답입니다!') : alert('오답입니다!');
```

위의 코드를 if문을 사용해 변형하면 아래와 같다.

```
let company = prompt('자바스크립트는 어떤 회사가 만들었을까요?', '');

if (company == 'Netscape') {
  alert('정답입니다!');
} else {
  alert('오답입니다!');
}
```

코드를 읽을 때 우리의 눈은 수직으로 움직인다.
수평으로 길게 늘어선 코드보단 여러 줄로 나뉘어 작성하는 것이 읽기 편하다.

물음표 연산자는 조건에 따라 반환 값을 달리하려는 목적으로 만들어졌다.

이런 목적에 부합하는 곳에 물음표를 사용하자.

여러 분기를 만들어 처리할 때는 if를 사용하자.