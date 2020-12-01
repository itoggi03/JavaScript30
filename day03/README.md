# Day03

> JS로 CSS 변수 업데이트 하기

<br>



## :root

아래처럼 root로 선언해놓고 계속 사용 가능

```jsx
:root {
      --base: #ffc600;
      --spacing: 10px;
      --blur: 10px;
    }

    img {
      padding: var(--spacing);
      background: var(--base);
      filter: blur(var(--blur))
    }
```