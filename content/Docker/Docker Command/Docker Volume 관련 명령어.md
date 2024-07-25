---
dg-publish: true
permalink: /docker/docker-command/docker-volume-commands
dgPassFrontmatter: true
---
### 볼륨 조작

-   다음은 `volume`를 상위 커맨드로 하는 볼륨 조작 관련 커맨드이다.
-   `docker volume 하위 커맨드 (옵션)` 형식으로 구성된다.

| **하위 커맨드** | **내용**           | **주요 옵션**          | **기타** |
| ---------- | ---------------- | ------------------ | ------ |
| create     | 볼륨 만들기           | \--name, --opt     |        |
| inspect    | 볼륨에 대한 자세한 정보 표시 | \--format          |        |
| ls         | 볼륨 목록 보기         | \--format, -filter |        |
| prune      | 불필요한 볼륨 삭제       | \--all, --filter   |        |
| rm         | 볼륨 삭제            | \--force           |        |
[[볼륨 마운트]]