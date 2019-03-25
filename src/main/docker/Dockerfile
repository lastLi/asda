# 基于 java的镜像
FROM anapsix/alpine-java:latest
# linux上面的挂载点为/tmp
VOLUME /tmp
# 添加一个jar为本项目的jar 第一个是打包的jar 第二个是别名
ADD demo-0.0.1-SNAPSHOT.jar demo.jar
# 执行 linux 命令  拷贝这个jar包到镜像
RUN bash -c 'touch /demo.jar'
# 暴露的端口号,application.yml端口号对齐
EXPOSE 8999
# 入口点 执行java jvm命令: 加快随机数产生过程,运行这个jar包
ENTRYPOINT [ "java", "-Djava.security.egd=file:/dev/./urandom", "-jar", "/demo.jar" ]
