#配置基础镜像，java:8为远程镜像，在构建镜像时会自动下载，如果本地已有，则直接使用
        FROM java:8
        #挂载本地/tmp文件夹到容器
        VOLUME /tmp
        #把此工程生成的jar包复制进容器内  路径为 /app.jar
        #ADD microservice-config-client-0.0.1-SNAPSHOT.jar app.jar
        #更改/app.jar的访问时间
        #RUN bash -c 'touch /app.jar'
        #指定容器需要映射到宿主机器的端口，需要与resources/application.properties 中设置的server.port 一致
        EXPOSE 8081
        #容器时启动时执行此命令 java.security.egd=file:/dev/./urandom 为tomcat启动优化项
        ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar"]