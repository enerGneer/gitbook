---
description: 분포도, 선택성
---

# Selectivity

### **선택성(Selectivity)**

* **Index를 구성하기 위해, 한 릴레이션에서 어떤 속성을 선택할지의 문제**
* 선택성이 좋다는 것은 수많은 데이터의 바다 속에서 내가 원하는 값만을 딱 집어올릴 수 있을 확률이 좋다는 것이다.
  * **선택성이 좋으려면 분포도가 낮아야 한다.**
    * **분포도가 낮다는 것은 자료가 밀집되어 있지 않고 중복이 적다는 뜻이다.**
* DB에서 "분포도가 좋다."라 표현하는 것은
  * _해당 컬럼의 유니크한 데이터 종류가 많다_ 라고 이해하면 된다.
* 분포도가 높다 = 선택성이 나쁘다 = 인덱스로 사용하기 안 좋다
* 선택성이 좋다 = 분포도가 낮다 = 인덱스로 사용하기 좋다

### 예시

#### 예시1

* 성별을 분석해보면 **분포도(selectivity)가 너무 안 좋다 (높다)**
  * 모든 자료의 값이 남/여 2가지중 하나라서
  * 선택성이 좋지 않은 = **분포도가 높은 예**
    * **성별. 남자/여자**로 나누는 경우 모집단의 반반으로 나뉘는 것 말고는 별 소득이 없을 것이다.
      * 이러한 데이터를 가지고 인덱스를 생성하면 효과를 보기보다는 오히려 손해를 본다

#### 예시2

* col\_1 컬럼 : 전체 건수 100건, 값들은 모두 A, B, C 의 3가지뿐일 경우
  * 분포도(selectivity) : **3%** (값/전체건수 : 3/100 \* 100)
* col\_2 컬럼 : 전체 건수 100건, 값들은 모두 1, 2, 3, 4, 5, 6 의 6가지일 경우
  * 분포도(selectivity) : **6%** (값/전체건수 : 6/100 \* 100)



### REF

* [https://jdm.kr/blog/169](https://jdm.kr/blog/169)
* [https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true\&blogId=kang\_sok\&logNo=60057985829](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true\&blogId=kang\_sok\&logNo=60057985829)
* [https://an-onymous.tistory.com/entry/Index-선택성-데이터베이스가-데이터를-빠르게-검색하는-방법](https://an-onymous.tistory.com/entry/Index-%EC%84%A0%ED%83%9D%EC%84%B1-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4%EA%B0%80-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%EB%B9%A0%EB%A5%B4%EA%B2%8C-%EA%B2%80%EC%83%89%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95)

