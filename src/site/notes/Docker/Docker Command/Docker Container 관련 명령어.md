---
{"dg-publish":true,"permalink":"/docker/docker-command/docker-container/","dgPassFrontmatter":true}
---

### 컨테이너 조작

-   다음은 `container`를 상위 커맨드로 하는 컨테이너 조작 관련 커맨드이다.
-   `docker conatiner 하위 커맨드 (옵션)` 형식으로 구성된다.

| **하위 커맨드** | **내용** | **주요 옵션** | **기타** |
| --- | --- | --- | --- |
| start | 컨테이너 실행 | \-i |   |
| stop | 컨테이너 정지 | 거의 사용하지 않음 |   |
| create | 컨테이너 생성 | \--name, -e, -p, -v |   |
| run | 도커 이미지를 내려받고, 컨테이너를 생성해 실행 | \--name, -e, -p, -v, -d, -i, -t | docker image pull + docker container create + docker container start 세 개의 명령어가 합쳐진 것과 같음 |
| rm | 정지 상태의 컨테이너를 삭제 | \-f, -v |   |
| exec | 실행 중인 컨테이너 속에서 프로그램 실행 | \-i, -t |   |
| ls | 컨테이너 목록을 출력 | \-a | 생략형 : docker ps |
| cp | 도커 컨테이너와 토커 호스트 간 파일을 복사 | 거의 사용하지 않음 |   |
| commit | 도커 컨테이너를 이미지로 변환 | 거의 사용하지 않음 |   |
[[Docker/Docker Command/컨테이너의 생성과 삭제, 실행, 정지\|컨테이너의 생성과 삭제, 실행, 정지]]
