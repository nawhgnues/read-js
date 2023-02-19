##### 1. statement

- 코드의 가독성을 높이기 위해 각 statement는 서로 다른 줄에 작성하는 것이 일반적.

```
console.log("hi");
console.log("bye");
```

- 줄 바꿈이 있다면 semicolon을 생략할 수 있다.
- 자바스크립트는 대부분의 경우 줄 바꿈이 있으면 이를 암시적 세미콜론으로 해석한다(automatic semicolon insertion)

```
// OK
console.log("hi")
console.log("bye")
```

- automatic semicolon insertion 예외
- [...] 대괄호 앞에서는 자동으로 세미콜론이 삽입되지 않는다.

```
// ERROR
console.log("error")
[1, 2].forEach(i => console.log(i))

위의 코드는 아래와 같다
console.log("error")[1, 2].forEach(i => console.log(i))

위의 코드 외에도 이런 상황이 발생할 여지는 언제나 있다
```

**2. comment**

- 주석을 달면 코드의 전체적인 길이가 증가하지만 서버 배포를 도와주는 도구들을 이용하면 주석은 자동으로 삭제된다.
- 최종적으로 배포되는 코드에는 부정적인 영향을 끼치지 않는다.
