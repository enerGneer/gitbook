# vars.css에 정의한 color에 opacity 값 부여하는 방법

hex값은 안된다고 해서 우선 hex값을 전부 rgb 값으로 변환했다. 그러나..

### 실패한 방법

```
:root {
  --bg-color: rgba(240, 240, 240);
  --bg-color-header: rgba(240, 240, 240, 0.8);
}

.notion-header {
  background-color: rgba(var(--bg-color), 0.8);
}
```

### 성공한 방법

```
:root {
  --bg-color: rgba(240, 240, 240);
  --bg-color-header: rgba(240, 240, 240, 0.8);
}

.notion-header {
  background-color: var(--bg-color-header);
}
```

## REF

[https://stackoverflow.com/questions/40010597/how-do-i-apply-opacity-to-a-css-color-variable](https://stackoverflow.com/questions/40010597/how-do-i-apply-opacity-to-a-css-color-variable)
