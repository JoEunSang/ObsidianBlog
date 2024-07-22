---
dg-publish: true
permalink: /docker/docker-command/docker-image-commands-share-image/
dgPassFrontmatter: true
---
### 레지스트리에 이미지 공유하기

#### 레지스트리, 리포지토리, 이미지 태그 다루기
-   전부터 Docker Registry와 Docker Repository의 개념이 굉장히 헷갈려 먼저 정리를 해 보았다.
    -   **Docker Registry** : Docker 이미지를 저장하고 관리하는 서비스로, 이미지를 push / pull 할 수 있다. Docker Hub가 가장 유명한 Registry이다.
    -   **Docker Repository** : 특정 이미지의 여러 버전을 모아 놓은 곳으로, 하나의 애플리케이션에 대한 여러 이미지에 대한 여러 버전을 모아 놓은 곳이다.
-   `docker search` 명령어를 통해 도커 허브에 등록된 리포지토리를 검색할 수 있다.
-   ![](https://i.imgur.com/BRTD7Ev.png)
-   도커 이미지 이름(이미지 참조)의 구조  
    ![](https://i.imgur.com/fwyvyo0.png)

#### 도커 허브에 직접 빌드한 이미지 push하기

-   도커 허브에 push를 하기 위해서는 먼저 도커 허브에 로그인을 해야 한다.
-   window 환경에서는 powershell을 사용하여 아래와 같이 로그인을 했다. id를 굳이 환경 변수로 저장하지 않고 바로 입력해도 무관하다.
-   ![](https://i.imgur.com/lAiOE22.png)
-   앞서 빌드 했던 image-of-day 이미지는 이미지 참조에 계정 이름이 없어 현재 상태로는 레지스트리에 push 할 수 없다.
-   ![](https://i.imgur.com/WklCOYa.png)
-   따라서 `docker image tag` 명령어를 사용해 기존 이미지에 새로운 이미지 참조를 부여하고, tag를 v1로 지정했다.
    -   ![](https://i.imgur.com/Z8hA0Uj.png)
    -   v1 태그를 갖는 `계정 이름/이미지 이름` 형식의 이미지가 생성된 모습이다.
    -   ![](https://i.imgur.com/ERYdnw1.png)
-   이제 push가 가능해졌을 테니 위의 이미지를 push해봤다.
    -   ![](https://i.imgur.com/L2lSNzm.png)
        
    -   Hub에 push 한 이미지는 따로 리스트에 업로드 되고, docker hub의 explore에 등록되어 다른 사람이 내가 push한 이미지를 다운 받을 수 있게 된다.
    -   ![](https://i.imgur.com/bGt18zW.png)
        
    -   ![](https://i.imgur.com/7de6siN.png)
        

#### 로컬 네트워크에 전용 레지스트리가 있으면 편리한 점은 무엇인가?

#### 이미지 태그를 효율적으로 사용하기

-   대부분의 소프트웨어 버전은 소수점으로 구분된 숫자로 나타내는 **버전 표현법**을 따른다.

💡**버전 표현법 이란?**  
\[major\].\[minor\].\[patch\] 형태의 표현법으로, patch 자리가 바뀌면 기능은 그대로 인 채 버그만 수정, minor 자리가 바뀌면 기존 기능을 유지한 채 추가된 기능이 있다는 뜻이고, major 자리가 바뀌면 기존 기능을 유지하지 않고, 다른 기능을 가지게 된다는 정보를 갖는다.

### 실용 도커 기술

#### 컨테이너와 호스트 사이에 파일 복사

-   컨테이너를 실행했다는 것은 다른 하나의 PC가 실행 중이라 봐도 된다.
-   이에 Docker는 내 Origin PC(Host)와 컨테이너 PC 간의 파일 이동을 위해 `cp`명령어를 지원한다.
-   현재 실행 중인 iotd의 app 디렉터리에 내 Host PC에 생성한 docker-cp-test라는 파일을 복사한 뒤 컨테이너를 실행해 확인해 보았다.
-   ![](https://i.imgur.com/LTxMl47.png)
-   반대로 컨테이너 내의 iotd-service-0.1.0.jar 파일을 Host PC에 복사해 가져 올 수도 있다.
-   하지만 어째서 인지 docker가 깔려있지도, 깔리지도 않아 확인할 수 없었다. 리눅스 환경에서 docker 설치 문제가 해결되면 다시 올려야겠다.
-   ![](https://i.imgur.com/LBogy7Y.png)
    -   참고 중인 내용(리눅스 환경에서 도커 설치) : [\[Docker\] Ubuntu 22.04 Docker 설치 (velog.io)](https://velog.io/@osk3856/Docker-Ubuntu-22.04-Docker-Installation)
    -   sudo 명령어를 찾을 수 없을 때 해결 방법 : [\[Error\]bash:command not found : 네이버 블로그 (naver.com)](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=rladnjsqll&logNo=221502853520)
