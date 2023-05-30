---
title: 'useState'
date: 2022-09-09 22:48:13
category: 'React&JS'
draft: false
---

## **1\. 개요**

`useState` Hook을 사용하면 함수형 컴포넌트에서 상태를 관리할 수 있다.

주로 값의 변경과 그에 따른 반영이 필요한 경우에 사용한다.

예를 들어, 버튼을 누를 때마다 값을 `true` 또는 `false`로 변경하거나, 버튼을 누를 때마다 값을 1씩 증가시키는 경우 등이 있다.

## **2\. 사용법**

우선 이 Hook을 사용하려면 import 해와야 한다.

```jsx
import { useState } from 'react'

export default function App() {}
```

import 해왔다면

```jsx
import { useState } from 'react'

export default function App() {
  const [count, setCount] = useState(0)
}
```

`const [변수명, count를 갱신할 수 있는 함수] = useState(초기값)` 형태로 작성하면 준비가 완료된다.

일반적으로 변수명과 `set`을 접두사로 사용하여 변수와 변수를 갱신하는 함수를 구분합니다.

초기값은 숫자, boolean, 객체, 배열 등 다양하게 설정할 수 있다.

```jsx
import { useState } from 'react'

export default function App() {
  const [count, setCount] = useState(0)
  return (
    <section>
      <h1>현재 카운트는 {count} 입니다.</h1>
      <button type="button" onClick={() => setCount(count + 1)}>
        증가
      </button>
      <button type="button" onClick={() => setCount(count - 1)}>
        감소
      </button>
      <button type="button" onClick={() => setCount(0)}>
        초기화
      </button>
    </section>
  )
}
```

위와 같이 `count` 값을 가져와 화면에 표시하거나 버튼을 눌렀을 때 값을 증가, 감소, 초기화할 수 있습니다.

![img (1)](https://github.com/wjdrk70/pre-onboarding-10th-1-6/assets/100986977/6460887f-3fac-4b46-8495-68ba603f175e)

## **3\. 주의사항**

`useState`는 비동기 Hook이다.

즉시 상태를 변경하지 않고, 컴포넌트가 다시 렌더링될 때까지 기다려야 한다.

즉시 상태를 변경하면 예상치 못한 동작이 발생할 수 있으므로 주의해야 한다.

<br>

**참고**

[https://javascript.plainenglish.io/why-you-shouldnt-always-use-usestate-658994693018](https://javascript.plainenglish.io/why-you-shouldnt-always-use-usestate-658994693018)

[https://www.w3schools.com/react/react_usestate.asp](https://www.w3schools.com/react/react_usestate.asp)

[https://ko.reactjs.org/docs/hooks-state.html](https://ko.reactjs.org/docs/hooks-state.html)
