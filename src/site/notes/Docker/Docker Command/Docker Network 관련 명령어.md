---
{"dg-publish":true,"permalink":"/docker/docker-command/docker-network/","dgPassFrontmatter":true}
---

### 네트워크 조작

-   다음은 `network`를 상위 커맨드로 하는 네트워크 조작 관련 커맨드이다.
-   `docker network 하위 커맨드 (옵션)` 형식으로 구성된다.

| **하위 커맨드** | **내용** | **주요 옵션** | **기타** |
| --- | --- | --- | --- |
| connect | 컨테이너를 네트워크에 연결 | \--ip, --link |   |
| create | 네트워크 만들기 | \--label |   |
| disconnect | 네트워크 컨테이너 끊기 | \--force |   |
| inspect | 네트워크에 대한 자세한 정보 보기 | \--force, --verbose |   |
| ls | 네트워크 목록 보기 | \--filter, --format |   |
| prune | 불필요한 네트워크 삭제 | \--filter, --force |   |
| rm | 네트워크 삭제 |   |   |
