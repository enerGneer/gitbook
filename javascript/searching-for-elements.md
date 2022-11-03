# Searching For Elements

## getElementById

* **getElementById** : Id를 가져올 수 있다.
  * `document.getElementById("id");`
* **getElementsByClassName** : array로 가져다준다
* **getElementsByName** : array로 가져다준다

## querySelector

* **querySelector**
  * css selector를 명시해줘야한다.
    * id를 가져오는 경우에는 `("#id")` 라고 입력한다.
  * 단 하나의 element만 return 해준다.
* **querySelectorAll**
  * 여러 element를 array로 가져오는 방법.

```javascript
document.querySelector(“.hello h1:first-child”)
document.getElementsByClassName(”hello”)
```
