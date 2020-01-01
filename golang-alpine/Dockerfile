FROM golang:alpine

# ############## author ##############
LABEL maintainer="fizzday <fizzday@yeah.net>" \
        Description="golang add dependency(gcc,libc-dev,git) with golang:alpine | latest"

# ############## env ##############
ENV TZ Asia/Shanghai
ENV PROXY ""
ENV GO111MODULE on

# ############## proxy ##############
RUN export GOPROXY=$PROXY

# ############## golang dependency ###########
RUN apk add gcc
RUN apk add libc-dev
RUN apk add --no-cache git