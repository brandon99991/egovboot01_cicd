# Spring Boot JAR 실행용 (가볍고 보편적)
FROM eclipse-temurin:17-jre
WORKDIR /app

# (선택) 컨테이너 시간대
ENV TZ=Asia/Seoul

# JAR 복사 (빌드 산출물 이름에 맞게 수정)
COPY ./egovboot01-1.0.0-SNAPSHOT.jar /app/egovboot01.jar

# (선택) JVM 옵션은 환경변수로 주입
ENV JAVA_OPTS=""

# Spring profile 등도 환경변수로 주입 가능
ENV SPRING_PROFILES_ACTIVE="prod"

EXPOSE 8080

# 셸 없이 exec-form 권장
ENTRYPOINT ["sh", "-c", "java $JAVA_OPTS -jar /app/egovboot01.jar --spring.profiles.active=$SPRING_PROFILES_ACTIVE"]
