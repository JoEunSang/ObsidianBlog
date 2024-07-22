---
{"dg-publish":true,"permalink":"/docker/docker-command/docker-image/","dgPassFrontmatter":true}
---

### 이미지 조작

-   다음은 `image`를 상위 커맨드로 하는 이미지 조작 관련 커맨드이다.
-   `docker image 하위 커맨드 (옵션)` 형식으로 구성된다.

| **하위 커맨드** | **내용** | **주요 옵션** | **기타** |
| --- | --- | --- | --- |
| build | Dockerfile로 이미지 빌드 | \--add-host, --tag, --pull |   |
| ls | 이미지 리스트 보기 | \-a, --format |   |
| pull | 레지스트리로부터 이미지 가져오기 | \-a, |   |
| push | 레지스트리에 이미지 전송 | \-a |   |
| rm | 이미지 삭제 | \-f | 생략형 docker rmi |

[[Docker/Docker Command/Image 공유\|Image 공유]]