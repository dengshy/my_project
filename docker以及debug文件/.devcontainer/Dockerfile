# 使用带有 CUDA 11.8 的 Ubuntu 20.04 基础镜像
FROM nvidia/cuda:11.8.0-devel-ubuntu20.04

# 设置环境变量，避免在安装过程中出现交互式提示
ENV DEBIAN_FRONTEND=noninteractive

# 更新包列表并安装 Python 3.8 和 pip
RUN apt-get update && \
    apt-get install -y python3.8 python3-pip && \
    apt-get clean

# 更新 pip 到最新版本
RUN python3 -m pip install --upgrade pip

# 设置默认的 Python 版本为 Python 3.8
RUN ln -s /usr/bin/python3.8 /usr/bin/python

# 设置工作目录
WORKDIR /workspace

# 确保使用 NVIDIA 驱动
ENV NVIDIA_VISIBLE_DEVICES all
ENV NVIDIA_DRIVER_CAPABILITIES compute,utility

# 启动时保持容器运行
CMD ["python"]
