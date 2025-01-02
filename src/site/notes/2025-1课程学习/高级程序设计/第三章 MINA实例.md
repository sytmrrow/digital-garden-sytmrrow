---
{"dg-publish":true,"tags":["信管课程"],"permalink":"/2025-1课程学习/高级程序设计/第三章 MINA实例/","dgPassFrontmatter":true,"created":"2025-01-01T15:58:37.329+08:00","updated":"2025-01-02T14:32:42.925+08:00"}
---

# 一、图片识别模型
前端：网页
网页调用php脚本，将图片上传的同时调用MINA的client端，将图片名称传输给后端
后端的MINA的server端接受到名字请求之后，回去对应路径下寻找图片，并将这个图片调用指定路径的模型，得到结果后将结果返回给MINA的client端，php将结果显示在网页端

过程中进行MINA通讯的时候，server端和client端的数据传输对象（请求数据和响应数据）及他们的encoder和decoder的方式是同步的