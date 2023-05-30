---
title: '이미지 프리뷰 구현'
date: 2022-09-19 01:11:13
category: 'React&JS'
draft: false
---

## **1.URL.createObjectURL()**

`URL.createObjectURL()`은 주어진 객체를 가리키는 URL을 DomString으로 반환하는 JavaScript 메서드이다.

이 URL은 해당 객체를 생성한 창의 document가 사라지면 무효화된다.

## **2\. 사용법**

```jsx
const objectURL = URL.createObjectURL(object)
```

여기서 `object`는 URL을 생성할 객체로서 File, Blob, 또는 MediaSource 등이 될 수 있다.

## **3\. 활용 예시**

먼저 input 요소를 생성한다.

```jsx
<input
  id="imageUploadInput"
  type="file"
  accept="image/*"
  ref={inpRef}
  onChange={handleImgPreview}
  className="ir"
/>
```

이 코드에서는 `input` 요소를 숨기고, 대신 `label`을 클릭할 때 `input`이 작동하도록 설정했다.

이미지 파일이 변경될 때, 다음과 같이 `handleImgPreview` 함수를 호출한다.

```jsx
// 이미지 미리보기
function handleImgPreview(e) {
  setPreview(URL.createObjectURL(e.target.files[0]))
}
```

이 코드는 변경된 이미지 파일에 대해 createObjectURL()을 사용하여 URL을 생성하고, 그 URL을 `setPreview` 함수를 통해 저장합니다.

위의 예시 코드는 하나의 이미지 파일만 처리하도록 설계되어 `files[0]`을 사용했습니다.

그러면 이렇게 짜잔!

![img](https://github.com/sabit1997/sabit1997.github.io/assets/100986977/ad55c0d5-e98e-451b-97d5-b38b767e207b)

📍틀린 부분이 있다면 말해주세요!

<br>

**참고**

[https://developer.mozilla.org/en-US/docs/Web/API/URL/createObjectURL](https://developer.mozilla.org/en-US/docs/Web/API/URL/createObjectURL)
