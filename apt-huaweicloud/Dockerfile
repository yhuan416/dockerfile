FROM ubuntu:22.04

LABEL top.yhuan.image.author="yhuan416 <yhuan416@foxmail.com>"
LABEL top.yhuan.image.apt-sources="repo.huaweicloud.com"

# set root passwd
RUN echo "root:root" | chpasswd

# timezone
RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    echo 'Asia/Shanghai' > /etc/timezone

# apt-get
WORKDIR /etc/apt
RUN cp sources.list sources.list.save && \
    sed -i "s@/archive.ubuntu.com@/repo.huaweicloud.com@g" sources.list && \
    sed -i "s@/security.ubuntu.com@/repo.huaweicloud.com@g" sources.list
RUN apt-get clean;apt-get update
