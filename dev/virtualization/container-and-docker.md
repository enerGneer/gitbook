# 컨테이너와 도커

## 컨테이너

기존의 VM(가상 시스템)은 컴퓨팅 인프라의 가상화를 지원하는 반면, 컨테이너는 소프트웨어 애플리케이션의 가상화를 지원한다.

가상 시스템과 달리 컨테이너는 자체 운영 체제를 제공하지 않고 호스트의 OS(운영 체제)를 이용한다.

#### 컨테이너의 필요성

전체 운영체제를 포함하고 있지 않기 때문에 최소한의 컴퓨팅 리소스만 필요로 하며, 빠르고 쉽게 설치할 수 있는 효율성.

이러한 효율성 덕분에 클러스터에 구축 가능,

개별 컨테이너들이 복잡한 애플리케이션의 단일 구성 요소를 캡슐화한다.

**개발자들은 각기 다른 컨테이너에 애플리케이션 구성 요소를 분리함으로써 전체 애플리케이션에 대한 재작업 없이 개별 구성 요소들을 업데이트 할 수 있다**.



## 도커 Docker

가장 널리 사용되는 컨테이너 기술.

일반적으로 컨테이너라고 하면 대부분 Docker를 가리킨다.