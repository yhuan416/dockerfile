FROM ubuntu:22.04

LABEL top.yhuan.image.author="yhuan416 <yhuan416@foxmail.com>"
LABEL top.yhuan.image.apt-sources="mirrors.tuna.tsinghua.edu.cn"

# set root passwd
RUN echo "root:root" | chpasswd

# timezone
RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    echo 'Asia/Shanghai' > /etc/timezone

# apt-get
WORKDIR /etc/apt
RUN cp sources.list sources.list.save && \
    sed -i "s@/archive.ubuntu.com@/mirrors.tuna.tsinghua.edu.cn@g" sources.list && \
    sed -i "s@/security.ubuntu.com@/mirrors.tuna.tsinghua.edu.cn@g" sources.list
RUN apt-get clean;apt-get update

# install tools
RUN apt-get install -y wget curl vim
