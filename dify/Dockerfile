# 使用 Go 1.22.2 作为基础镜像
FROM golang:1.22.2-bullseye

# 设置 Go module 代理
ENV GOPROXY=https://goproxy.cn,direct

# 在容器内部创建工作目录
WORKDIR /app

# 将工作目录设为 GOPATH。这样做可以优化构建缓存并加快构建速度
ENV GOPATH=/app

# 将主机上当前目录下的内容复制到容器内的 /app 目录中
COPY . .

# 下载所有依赖
RUN go mod download

# 构建所有 go 文件
RUN go build -o main .

# 镜像运行时应该执行的命令
CMD ["./main"]
