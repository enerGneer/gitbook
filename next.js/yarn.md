# yarn

동시에 여러 개의 패키지들을 다운로드. 처음에 한 번 세팅을 해두면 시간적인 측면에서 편리하게 사용 가능.

### install & setting

* npm을 통해 설치.
  * `npm install -g yarn`
  * \-g = global
  * yarn이 설치된 컴퓨터 어디에서든 yarn을 사용 가능하다는 뜻.
  * 설치 여부 확인방법은 `yarn --version`.
* 따로 yarn 폴더를 생성하여 필요한 최신 라이브러리를 다운로드하여 프로젝트 폴더로 이동하는 방법 추천.
  * yarn을 Install 할 때 여러 개의 파일이 생성되는데, 웹퍼블리싱에는 필요하지 않은 파일이기 때문.

#### 따라서 따로 yarn 폴더를 생성하여 아래와 같은 과정을 마쳐두었다.

1. yarn 실행할 곳으로 이동 `cd 경로` -> 생성 `yarn`
   * 빈 폴더에 node-modules폴더가 생성됨. yarn을 사용할 수 있는 환경 세팅.
2. 폴더에 package.json 생성
   * `yarn init`
   * 라이브러리 디펜던시스와 연결 가능
3. 사용하고자 하는 라이브러리와 연결
   * `yarn add [package]` 최신버전 다운로드
   * `yarn add [package@version]` 버전설정하여 다운로드
4. 연결된 라이브러리 다운로드
   * `yarn install`

#### 이제 다운로드 완료된 라이브러리들을 폴더로 복사해서 사용하면 된다.

### Troubleshooting

#### 문제가 발생할 시

* `npm i`
  * 웬만한 npm 문제는 npm i 로 해결되는 듯 하다.
* `npm update`

#### VS Code Terminal에서 yarn 실행이 안되는 문제

1. Windows PowerShell 을 관리자 권한으로 실행
2. 주어진 권한 상태 확인(get-ExecutionPolicy) : restrict로 되어있을 것
3. Set-ExecutionPolicy RemoteSigned 입력 -> y : remotesigned로 변경
4. 그 이후에도 문제가 생겨서 결국 powershell이 아닌 Git bash로 하니까 해결되었다.\
   이때의 문제는 아래의 에러메시지 해결 명령어가 실행이 안 되는 것이었다.

#### ENOENT: no such file or directory

* `rm -rf node_modules package-lock.json`
* `-rf`\
  \-r : 하위 디렉토리를 포함한 파일들을 모두 삭제\
  \-f : 삭제할 것인가를 메시지 없이 그대로 강제 삭제
  * 즉, 모듈을 모두 삭제하고 다시 설치하는 것.



## :link: REF

* https://someone-life.tistory.com/39
* https://www.biew.co.kr/entry/Yarn-Package-Manager-%EC%84%A4%EC%B9%98-%EB%B0%8F-%EC%82%AC%EC%9A%A9%EB%B0%A9%EB%B2%95%EC%82%AC%EC%9A%A9-%EA%B0%80%EC%9D%B4%EB%93%9C
* https://choonse.com/2021/06/25/101/
* https://doozi316.github.io/errorlog/2020/07/10/error6/
* https://velog.io/@kkyu0718/Remove-Item-%EB%A7%A4%EA%B0%9C-%EB%B3%80%EC%88%98-%EC%9D%B4%EB%A6%84-rf%EA%B3%BC%EC%99%80-%EC%9D%BC%EC%B9%98%ED%95%98%EB%8A%94-%EB%A7%A4%EA%B0%9C-%EB%B3%80%EC%88%98%EB%A5%BC-%EC%B0%BE%EC%9D%84-%EC%88%98-%EC%97%86%EC%8A%B5%EB%8B%88%EB%8B%A4
* https://hhyemi.github.io/2021/05/26/nextGit.html
* https://ahnheejong.name/articles/remaking-blog/
