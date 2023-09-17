# 개발 서버(Dev), 스테이징 서버(Stg), 운영 서버(Prod)

#### - 개발 서버(Dev) <a href="#ea-b-c-eb-b-c-ec-c-eb-b-dev" id="ea-b-c-eb-b-c-ec-c-eb-b-dev"></a>

테스트용 서버로, 개발자들이 마음대로 테이블이나 서비스를 추가,수정,삭제 하면 여러가지 서비스를 테스트 할 수 있는 자유로운 서버이다.

ex) 개발서버에서 형상관리에 커밋된 파일이나 ftp등의 업로드 수정&#x20;

&#x20;

#### - 스테이징 서버(Stg) <a href="#ec-a-a-ed-c-ec-d-b-ec-a-ec-c-eb-b-stg" id="ec-a-a-ed-c-ec-d-b-ec-a-ec-c-eb-b-stg"></a>

운영 서버의 클론 서버처럼 똑같이 운영되는 서버로서 스테이징에서 문제가 없으면 운영 서버에 그대로 배포하기 위한 최종 검수하는 테스트 서버이다. (최종 검수 환경이기 때문에 개발 팀 뿐 아니라 기획팀이나 어떤 클라이언트 업체에게 공유하여 중간보고나 스테이징 도메인을 기준으로 시연하기도 한다.)

ex) 스테이싱 서버에서 형상관리로 커밋된 파일들이 어떤건지 추리고 올려서 확인

&#x20;

#### - 운영 서버(Prod) <a href="#ec-a-b-ec-ec-c-eb-b-prod" id="ec-a-b-ec-ec-c-eb-b-prod"></a>

실제 스테이징 서버에서 정상 반영된 경우 운영서버에 해당 부분을 반영하는 운영 서버이다.



[https://lee-automation-lab.tistory.com/entry/IT-%EC%9A%A9%EC%96%B4-%EA%B0%9C%EB%B0%9C-%EC%84%9C%EB%B2%84Dev-%EC%8A%A4%ED%85%8C%EC%9D%B4%EC%A7%95-%EC%84%9C%EB%B2%84Stg-%EC%9A%B4%EC%98%81-%EC%84%9C%EB%B2%84Prod](https://lee-automation-lab.tistory.com/entry/IT-%EC%9A%A9%EC%96%B4-%EA%B0%9C%EB%B0%9C-%EC%84%9C%EB%B2%84Dev-%EC%8A%A4%ED%85%8C%EC%9D%B4%EC%A7%95-%EC%84%9C%EB%B2%84Stg-%EC%9A%B4%EC%98%81-%EC%84%9C%EB%B2%84Prod)
