# Hexagonal architecture (= Port & Adapter architecture)

* 육각형 안쪽에 도메인과 관련된 비즈니스 로직이 들어가고, 육각형 바깥에 도메인과 상관이 없는 인프라 코드가 들어감
* Adapter: 외부에서 들어오거나 나가는 요청을 처리 하는 부분 (port를 통하기 위해 거쳐야 하는 부분) Port: Adapter와 비지니스 로직 접근하는 통로 (input, output 통로)
