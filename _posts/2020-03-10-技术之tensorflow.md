---
layout:     post
title:      技术之tensorflow
date:       2020-02-13
author:     cyq
catalog: true
tags:
    - 技术

---



## tensorflow

#### GPU版本安装

https://blog.csdn.net/m0_38055352/article/details/92064188

- 先根据 gpu 驱动版本安装合适版本的cuda tookit
- 然后按照cuda tookit版本安装合适的版本tensorflow-gpu（会自动识别并安装需要的cudnn）

注：四者版本一定要兼容。

#### GPU使用

- 如果要使用gpu，则需要删掉cpu的安装包，要不然会默认用cpu。

- 指定用的gpu核：

  只使用核1：CUDA_VISIBLE_DEVICES=1  python your_file.py

  使用多个：CUDA_VISIBLE_DEVICES=0,2,3   python your_file.py

  后台执行：CUDA_VISIBLE_DEVICES=1 nohup python file.py > log.txt  2>&1 &

#### tensorboard使用

- 服务器远程的tensorboard

  本地连接服务器时：ssh -L 16006:127.0.0.1:6006 用户名@服务器ip

  然后在服务器端执行：tensorboard --logdir="/path/to/log-directory“

  本地打开浏览器：http://127.0.0.1:16006/

