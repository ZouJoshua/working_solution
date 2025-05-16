# This vision_insight Dockerfile
# Version 1.0

# Base images 基础镜像
#FROM continuumio/miniconda3:4.11.0
#FROM nvidia/cuda:10.0-runtime-centos7
#FROM nvidia/cuda:11.3.1-cudnn8-devel-centos7
#FROM pytorch/pytorch:1.12.0-cuda11.3-cudnn8-devel
FROM nvcr.io/nvidia/pytorch:21.06-py3

#MAINTAINER 维护者信息
MAINTAINER Joshua

WORKDIR /app
RUN mkdir -p /app/ChatGLM2-6B
RUN mkdir -p /app/models/chatglm2-6b
COPY ./ /app/ChatGLM2-6B

#RUN sed -i -e "s/deb.debian.org/mirrors.tuna.tsinghua.edu.cn/" /etc/apt/sources.list && \
#    sed -i -e "s/security.debian.org/mirrors.tuna.tsinghua.edu.cn/" /etc/apt/sources.list && \
#    apt update
#RUN apt install -y libgl1-mesa-glx
# 清华源
#https://pypi.tuna.tsinghua.edu.cn/simple
# 阿里云
#http://mirrors.aliyun.com/pypi/simple
# 百度
#https://mirror.baidu.com/pypi/simple
# 中科大
#https://pypi.mirrors.ustc.edu.cn/simple
# 豆瓣
#http://pypi.douban.com/simple
ENV PIP_ROOT_USER_ACTION=ignore
ENV LANG "en_US.UTF-8"

RUN pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple && \
    pip install --upgrade pip && \
    pip install -r ./ChatGLM2-6B/requirements.txt && \
    pip install --user protobuf==3.20.1