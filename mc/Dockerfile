FROM ubuntu:20.04

# 更新软件包并安装Java和必要工具
RUN apt-get update && apt-get install -y \
    openjdk-17-jre-headless \
    wget \
    screen \
    && rm -rf /var/lib/apt/lists/*

# 创建Minecraft服务器目录
RUN mkdir -p /opt/minecraft

# 设置工作目录
WORKDIR /opt/minecraft

# 下载Minecraft服务器JAR文件
RUN wget https://launcher.mojang.com/v1/objects/1b557e7b033b583cd9f66746b7a9ab1ec1673ced/server.jar

# 接受EULA
RUN echo "eula=true" > eula.txt

# 暴露Minecraft服务器端口
EXPOSE 25565

# 启动Minecraft服务器
CMD ["java", "-Xmx4G", "-Xms1G", "-jar", "server.jar", "nogui"]