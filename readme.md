# golang-dependency
golang运行环境, 依赖 `golang:alpine`, 添加了 gcc,libc-dev,git 依赖

## dockerfile
```
FROM golang:alpine

# ############## author ##############
LABEL maintainer="fizzday <fizzday@yeah.net>" \
        Description="golang add dependency(gcc,libc-dev,git) with golang:alpine | latest"

# ############## env ##############
ENV TZ Asia/Shanghai
ENV PROXY ""
ENV GO111MODULE on
ENV GOPRODIR /go/src

# ############## proxy ##############
RUN export GOPROXY=$PROXY

# ############## golang dependency ###########
RUN apk add --no-cache gcc
RUN apk add --no-cache libc-dev
RUN apk add --no-cache git

# ############## work dir ###########
RUN mkdir -p $GOPRODIR

WORKDIR $GOPRODIR
```