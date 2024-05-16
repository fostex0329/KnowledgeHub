# ベースイメージとしてOpenJDKを使用
FROM openjdk:17-jdk-slim

# JARファイルを配置するディレクトリを作成
VOLUME /tmp

# アプリケーションのJARファイルを追加
COPY target/KnowledgeHub.jar app.jar

# アプリケーションを起動
ENTRYPOINT ["java","-jar","/app.jar"]
