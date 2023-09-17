# E2E test

종단(Endpoint) 간 테스트.

* 개발물을 사용자 관점에서 테스트 하는 방법.
  * 페이지에서 원하는 텍스트가 제대로 출력이 되었는지, 버튼을 클릭 했을 때 올바른 동작을 수행하는 지 등을 테스트한다.
* 애플리케이션의 흐름을 처음부터 끝까지 테스트하는 것.
  * 유닛 테스트나 통합 테스트는 모듈의 무결성을 증명할 수 있는 강력한 테스트이지만, 모듈의 무결성이 애플리케이션 동작의 무결성까지는 증명해 줄 수 없습니다. 그래서 E2E 테스트 과정에서는 실제 사용자의 시나리오를 테스트함으로써 애플리케이션 동작을 테스트하게 되고, 이 테스트를 통과함으로써 애플리케이션의 무결성을 증명할 수 있게 됩니다.

Endpoint 테스트를 통과하면 기능이 잘 작동한다는 것이므로 모든 테스트를 할 수 없다면 E2E Test만이라도 하는 것이 좋다.

E2E 테스트는 비용이 많이 드는 만큼 꼭 필요한 테스트만 수행해야 한다.



{% embed url="https://velog.io/@hoonki/E2E-%ED%85%8C%EC%8A%A4%ED%8A%B8%EB%8A%94-%EA%B7%B8%EB%A7%8C.-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EA%B0%9C%EC%84%A0%EA%B8%B0" %}

{% embed url="https://medium.com/delivus/e2e-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EA%B5%AC%EC%B6%95%EA%B8%B0-used-aws-step-functions-2fccb930218c" %}

{% embed url="https://fe-developers.kakaoent.com/2023/230209-e2e/" %}

{% embed url="https://blog.hbsmith.io/e2e-test-%EC%95%8C%EC%95%84%EB%B3%B4%EA%B8%B0-3c524862469d" %}

{% embed url="https://hyg4196.tistory.com/127" %}
