# # SOURCE
# FROM alpine as source
# RUN ln -snf /usr/share/zoneinfo/Asia/Seoul /etc/localtime
# RUN echo Asia/Seoul > /etc/timezone

# WORKDIR /project
# COPY . .


# # BUILD (INCLUDE TEST)
# FROM azul/zulu-openjdk-alpine:17-latest AS build
# RUN ln -snf /usr/share/zoneinfo/Asia/Seoul /etc/localtime
# RUN echo Asia/Seoul > /etc/timezone

# WORKDIR /project
# COPY --from=source project .

# ENTRYPOINT ["./gradlew", "build"]


# # RUNNER
# FROM azul/zulu-openjdk-alpine:17-jre-latest AS runner
# RUN ln -snf /usr/share/zoneinfo/Asia/Seoul /etc/localtime
# RUN echo Asia/Seoul > /etc/timezone

# WORKDIR /project

# COPY --from=build project/build/libs/*.jar app.jar

# ENTRYPOINT ["java", "-jar", "app.jar"]

FROM azul/zulu-openjdk-alpine:17-jre-latest AS runner
RUN ln -snf /usr/share/zoneinfo/Asia/Seoul /etc/localtime
RUN echo Asia/Seoul > /etc/timezone

WORKDIR /app

COPY build/libs/*.jar app.jar
EXPOSE 8080

ENTRYPOINT ["java", "-jar", "app.jar"]
