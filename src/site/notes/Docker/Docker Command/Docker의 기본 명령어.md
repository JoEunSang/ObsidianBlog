---
{"dg-publish":true,"permalink":"/docker/docker-command/docker/","dgPassFrontmatter":true}
---

## 컨테이너의 기본적인 사용법

### 도커 명령어

-   컨테이너 사용의 기본은 도커 명령어 이다.
-   모든 명령은 `docker` 명령어로 시작한다.
-   도커 명령어는 `docker 커맨드 대상` 으로 구성된다.
    -   `docker` 명령어 뒤에 오는 내용을 커맨드라고 한다.
        -   커맨드는 상위 커맨드와 하위 커맨드로 나뉘는데, 상위 커맨드는 ‘무엇을’, 하위 커맨드는 '어떻게’에 해당되는 내용을 지정한다.
    -   커맨드 뒤에 오는 내용은 ‘대상’ 으로 컨테이너 명 또는 이미지 명 등이 들어 간다.

### 기본적인 명령어 구조 정리

-   기본적인 명령어는 다음과 같다.
    -   `docker 커맨드 (옵션) 대상 (인자)`
-   옵션은 커맨드에 구체적인 설정을 지정하는 용도로 쓰인다
-   인자는 대상에 전달할 값을 지정한다.

### version 명령어를 사용해보자

-   version 명령어는 docker의; 버전을 확인하는 명령어다.
-   ![](https://i.imgur.com/ycdvMAy.png)

## 조작 관련 커맨드 정리

-   `docker` 명령을 시작으로 상위 커맨드에는 대표적으로 `container`, `image`, `volume`, `network` 가 있다.
[[Docker/Docker Command/Docker Container 관련 명령어\|Docker Container 관련 명령어]]
[[Docker/Docker Command/Docker Image 관련 명령어\|Docker Image 관련 명령어]]
[[Docker/Docker Command/Docker Volume 관련 명령어\|Docker Volume 관련 명령어]]
[[Docker/Docker Command/Docker Network 관련 명령어\|Docker Network 관련 명령어]]
### 그 밖의 상위 커맨드

| **커맨드** | **내용** |
| --- | --- |
| builder | 빌드 관련 관리 커맨드 |
| checkpoint | 체크 포인트 관리 커맨드 |
| config | Docker 설정 관리 커맨드 |
| system | Docker 관리 커맨드 |
| plugin | 플러그인 관리 커맨드 |
| trust | 이미지 서명 관리 커맨드 |
| manifast | 매니페스트 관리 커맨드 |

### 단독으로 쓰는 커맨드

| **커맨드** | **내용** |
| --- | --- |
| login | Docker 레지스트리에 로그인 |
| logout | Docker 레지스트리에 로그아웃 |
| version | Docker 버전 정보 보기 |
| search | Docker Hub에서 이미지 검색 |
