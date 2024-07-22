---
{"dg-publish":true,"permalink":"/docker/about-docker/docker/","dgPassFrontmatter":true}
---

##### 실습환경 구축하기

-   도커 데스크톱의 첫 실행 및 화면 확인(캡쳐)
-   도커 컨테이너를 다루는 명령어 알아보기
    -   컨테이너 생성 : `docker create {옵션} --name {컨테이너 이름} {이미지 repository}`
    -   컨테이너 생성 후 실행 : `docker run --name {컨테이너 이름} {옵션} -p {호스트 포트}:{컨테이너 포트}{이미지 repository}`
    -   컨테이너 이름 변경 : `docker rename {기존 이름} {변경할 이름}`
    -   컨테이너 상태 리스트 확인
        -   실행 중인 컨테이너 리스트 : `docker ps`
        -   모든 컨테이너 리스트 : `docker container ps -a`
    -   컨테이너 실행 : `docker start {이미지 이름:태그}`
    -   특정 컨테이너 중지 : `docker stop {컨테이너 id 또는 이름}`
    -   모든 컨테이너 중지 : `docker stop $(docker ps -aq)`
    -   컨테이너 삭제 : `docker rm {컨테이너 id 또는 이름}`
    -   실행 중인 컨테이너 내부 접속 : `docker exec -it {컨테이너 id 또는 이름} /bin/bash 또는 docker attach {이미지 이름:태그}`
    -   실행 중인 컨테이너 접속 종료 : `exit or ctrl + D`
-   도커 컨테이너를 프롬프트로 다룰 때 주의할 점
    -   관리자 권한으로 실행해야 한다
-   컨테이너로 Hello World 실행하기
    -   `docker pull hello-world` 커맨드로 이미지를 다운 받고, `docker run hello-world` 커맨드로 실행한다.
    -   ![](https://i.imgur.com/rhWMyVM.png)
    -   hello-world를 실행하면 docker의 동작 과정이 나온다.
    -   ![](https://i.imgur.com/oabk9PM.png)
-   Apache 서버로 웹페이지 출력하기
    -   Apache의 경우 httpd 라는 이름을 사용한다.
        -   ![](https://i.imgur.com/EI1eZ6v.png)
    -   `docker pull httpd` 커맨드로 이미지를 다운 받는다.![](https://i.imgur.com/H1CYQ3c.png)
    -   `docker run --name container이름 -p (사용할 pid):(사용할 포트(80))` 로 컨테이너를 실행한다.![](https://i.imgur.com/XLwBatq.png)![](https://i.imgur.com/2gJIf4c.png)
-   Nginx 서버로 웹페이지 출력하기
    -   nginx의 경우도 Apache와 동일한 과정으로 이미지를 다운 받는다.
    -   이번엔 docker desktop으로 실행 시켜보겠다.
        -   별건 없고 images에 들어가 다운 받은 nginx의 이미지를 run 버튼을 통해 실행 시켜주면 된다![](https://i.imgur.com/oKjKwWH.png)
        -   실행할 경우 아래와 같은 로그들이 뜬다.![](https://i.imgur.com/eFuMaDe.png)![](https://i.imgur.com/uNERJl5.png)