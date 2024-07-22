---
dg-publish: true
permalink: /docker/docker-file/gradle-based-docker-file/
dgPassFrontmatter: true
---
### gradle 기반의 Spring 웹 서버를 Dockerfile로 만들자.

위 실습을 위해 예전에 프로젝트로 진행했던 Springboot 서버 프로그램을 가져왔다.  
우선 Build Stage와 Run Stage로 나눈 멀티 스테이지 방식으로 Dockerfile을 작성했다. 책과 예제를 참고 했던 maven 기반의 Dockerfile 작성과는 달리, 실제로 진행했던 프로그램의 Dockerfile을 작성하려니 생각보다 여러 이슈가 생겼다.

1.  git에서 빌드 할 프로젝트를 clone 한 후, `./gradlew clean build` 명령어로 기존 파일을 지우고 새로 빌드한다.  
    ![](https://i.imgur.com/s60aSux.png)
2.  해당 프로젝트의 root 폴더에 Dockerfile을 생성하고 작성한다.  
    ![](https://i.imgur.com/d0w3csF.png)
3.  도커 파일은 build.gradle에서 해당 프로젝트의 jdk 버전을 참고하여 작성한다.

```
# 빌드 스테이지  
FROM gradle:7.4-jdk17-alpine AS build  
# 작업 디렉토리 설정  
WORKDIR /build  
# 소스 코드와 빌드 스크립트 복사  
COPY build.gradle settings.gradle /build/  
RUN gradle build -x test --parallel --continue > /dev/null 2>&1 || true  
 
COPY . /build  
RUN gradle build -x test --parallel  
 
# 런타임 스테이지  
FROM openjdk:17-jdk-slim  
 
# 작업 디렉토리 설정  
WORKDIR /app  
 
# 빌드 스테이지에서 생성된 JAR 파일을 현재 스테이지로 복사  
COPY --from=build /build/build/libs/*-SNAPSHOT.jar ./app.jar  
 
# 애플리케이션 실행  
ENTRYPOINT ["java", "-jar", "app.jar"]  
 
# 애플리케이션 포트 노출  
EXPOSE 8080
```

-   Dockerfile 작성은 해당 블로그를 참고하여 작성하였다. ([\[Docker\] gradle로 빌드하여 도커로 배포하기 (velog.io)](https://velog.io/@coastby/Docker-gradle%EB%A1%9C-%EB%B9%8C%EB%93%9C%ED%95%98%EC%97%AC-%EB%8F%84%EC%BB%A4%EB%A1%9C-%EB%B0%B0%ED%8F%AC%ED%95%98%EA%B8%B0))  

