---
description: JavaScrispt에서 작업할 대부분의 일은, event를 listen하는 것이다.
---

# Event

## Basic

1. element를 찾아라.
2. event를 listen하라.
3. event 발생 시 반응하라.

### event란?

* 예를 들어 click, mouse over, 입력을 끝냄, 내 이름을 적고 enter를 누름, wifi에서 접속이 해제됨 등

### listen하고 싶은 event 찾는 방법

1. 찾고싶은 element의 이름을 Web APIs MDN(Mozilla Developer Network)에 검색
   * JS 관점의 HTMLHeadingElement라는 의미
   * ex. h1 html element mdn
2. **console.dir**로 입력해보기 : element의 내부를 보고싶을 때
   * 사용 가능한 event들을 알려준다.
   * 앞에 on이 붙은 것이 event listener
   * 이 event를 사용할 때에는 on을 떼고 사용해야 한다.
     * mouseenter: 마우스로 클릭은 안 하고 그냥 위로 올릴 때



## Event Listener를 사용하는 방법 2가지

{% tabs %}
{% tab title="1" %}
`title.addEventListener("click", handleTitleClick);`

* 이 방식은 나중에 remove를 추가해서 이벤트를 지울 수 있기 때문에 좋다.
{% endtab %}

{% tab title="2" %}
`title.onclick = handleTitleClick;`

* on + eventname
{% endtab %}
{% endtabs %}

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><h3>document</h3></td><td><p><code>document.body.</code></p><ul><li><p>HTML의 요소 중 body, title, head 등 특별한 부분만 호출 가능.</p><ul><li>예를 들어 div는 불가하다.</li></ul></li></ul></td></tr><tr><td><h3>window</h3></td><td><p>document처럼 기본적으로 탑재되어있다.</p><p>말 그대로 ‘창’에 대한 것.</p></td></tr></tbody></table>



## Getter & Setter

```javascript
function handleTitleClick() {
  console.log(h1.style.color); // [getter] h1의 color를 get할 수 있다.
  h1.style.color = "blue"; // [setter] h1의 color를 set할 수 있다.
  console.log(h1.style.color); // get again
}
```



## class 전달하는 법

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th></tr></thead><tbody><tr><td><h3>ClassName</h3></td><td>이전 class들과 관계없이 모든 class를 교체해버린다.</td></tr><tr><td><h3>ClassList</h3></td><td>Class의 목록으로 작업할 수 있도록 해준다.</td></tr></tbody></table>

<details>

<summary>functions</summary>

[https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList)

* constains
  * Returns `true` if the list contains the given token, otherwise `false`.
* add
  * Adds the specified tokens to the list.
* remove
  * Removes the specified tokens from the list.
* toggle
  * Removes the token from the list if it exists, or adds it to the list if it doesn't. Returns a boolean indicating whether the token is in the list after the operation.

</details>
