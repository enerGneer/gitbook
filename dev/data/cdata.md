# CDATA

* (Unparsed) Character Data
* xml을 파싱하기 위해 사용되는 것
* xml에 보면 \<!\[CDATA\[내용]] 이런 코드로 사용함. 파싱되지 않은 문자라는 의미
* 주로 쿼리에서 많이 사용함



* SELECT문에는 조건을 걸어 쿼리하기 위해 <, >, = 등의 기호를 많이 사용하는데, 이것이 파싱 중에 태그로 인식되거나 하는 등의 문제가 생길 수 있다.&#x20;
  * &#x20;\<!\[CDATA\[  ]]> 안에 원하는 쿼리문을 선언 한다면, 파싱하지 않고 그대로 문자열로 인식 시킬 수 있어 이런 문제를 예방할 수 있다.
* 주의 할 것은, CDATA 영역 안의 모든 < , >를 문자열로 만들어버리기 때문에 동적 쿼리를 작성하는 곳에는 주의해서 사용합니다. 직접 해당 기호가 들어가는 곳에 사용해야 합니다.



{% embed url="https://gdtbgl93.tistory.com/53" %}

{% embed url="https://escapefromcoding.tistory.com/372" %}