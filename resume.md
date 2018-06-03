# 简历

更新日期：2018.6.3

## 基本信息

- 姓名：刘德忠
- 出生日期：1994.1
- 婚姻状况：未婚
- 政治面貌：团员
- 籍贯：江西赣州
- 民族：汉
- 住址：上海
- 联系方式：
  - 电话：
  - email：ldz1943@163.com
- 家庭成员：

## 教育背景

- 2012.9 ~ 2016.6：南昌大学 - 软件工程本科

## 工作履历

- 2018.1 ~ 2018.6：华云数据[上海] - DevOps 工程师（负责 jenkins 打包自动化、gerrit 门禁、tempest）

- 2016.5 ~ 2017.12：软通动力[杭州] - Python 开发工程师（外包在华为杭研做云计算基础服务开发）

```text
我们小组负责的基础服务包括 keystone、rabbitmq、gaussdb、ntp、log、healthcheck 等，和相邻的安装部署小组一起组成整个集成部门。

作为组内开发，主要负责模块需求开发以及问题单解决。
我在这边先是从一个基础自研模块的测试用例开始的。期间我详细研读了该模块的历史代码，并顺着模块间关系学习，对华为云有了初步的认识。之后是开发需求以及问题单解决，慢慢地接触到其它模块，渐渐对组内业务有了全面的认识。经过多次尝试后，终于从keystone开始打开了对于原生组件的学习之门，一切都是自己加班时间自学的。

2017.5~2017.11，推荐到运维小组 oncall 现网（五朵公有云）问题。
我在很短的时间内熟悉了相邻项目组的业务知识，对原项目组的知识也有了更深层次的掌握，此外我还自学了 nova 的源码、了解了 neutron 的架构，对 OpenStack 有了整体的认知。在现网问题接口的6个月里，我先后自主攻关问题10余个，主动学习掌握运维基本知识。

最后回归项目组做 rabbitmq 开发。
```

## 专业技能

- 基础知识
  - 体系结构
  - 操作系统
  - 编译原理
  - 算法
  - 网络
- 编程平台
  - JavaScript
  - C
  - Java
  - Python
    - 数据结构
      - list
      - tuple
      - dict
      - set
      - collections
      - queue
      - heapq
    - 高级语法
      - 列表、字典推导
      - 装饰器
      - 生成器
      - 上下文管理器
      - 协议方法
      - 描述符
      - metaclass
      - async
    - 标准库
      - os, sys, pdb, traceback
      - threading, multiprocessing
      - itertools
      - logging
      - unittest
      - re, json
      - argparse, configparser, subprocess
      - socket, http, wsgiref, urllib
    - 第三方库
      - requests
      - sqlalchemy
      - eventlet
      - paramiko
      - celery
      - supervisor
      - schema
      - cliff
      - pillow
      - webob, pecan, flask, django, tornado, twisted, scrapy
      - numpy, scipy, matplotlib, scikit-learn
    - venv & tox
    - jupyter
  - Erlang
  - Lisp
- 技术领域
  - Web
  - App
  - 游戏
  - Qt
  - [x] 分布式 & 中间件
    - PostgreSQL
    - RabbitMQ
    - Apache
    - Nginx
    - HAProxy
    - Zookeeper
  - [x] DevOps
    - Jenkins
    - Ansible
    - Docker
    - Zabbix
  - [x] [OpenStack](https://www.openstack.org/software/)
    - keystone
    ```text
    user 是API 调用者
    user 拥有 credentials，比如 user/password，token 等
    token 相当于是用户信息的加密形式，方便在服务请求时携带。
    keystone token 的类型：uuid、pki（可离线验证、长度大、需持久化）、pkiz、fernet
    user 归属于0个或多个 group
    当 user 访问某服务时，该服务会通过 keystone middleware 对其进行身份认证，认证过后再通过服务自身的 policy.json 基于 role 对该用户的行为进行鉴权，最终返回结果。（前提是该服务使用keystone进行认证并且已注册）
    project 代表资源划分，每个 user 必须归属它需要访问资源的 project，user 可以归属多个 project
    在一个 domain 中 user、group、project 是唯一的，role 是全局的。
    endpoint 即服务入口 url
    region 可以理解为地理上的隔离，每个 region 可以有独立完整的 openstack 部署环境
    service 拥有 endpoints，这些 endpoints 可以属于不同的 region（所以 keystone 是可以跨 region 的）

    keystone identity 对接 ldap
    ```
    - glance
    - nova
      - 子服务
      ```text
      nova-api、nova-compute、nova-scheduler、nova-conductor等

      创建虚机调用过程：
      nova.api.openstack.compute:APIRouterV21.factory -> ROUTE_LIST '/servers/{id}/action'

      nova.api.openstack.compute.servers.ServersController.create

      nova.compute.API.create -> _create_instance

      if CONF.cells.enable:
          nova.conductor.api.ComputeTaskAPI.build_instances -> nova.conductor.rpcapi.ComputeTaskAPI.build_instances -> nova.conductor.manager.ComputeTaskManager.build_instances

          nova.compute.rpcapi.ComputeAPI.build_and_run_instance -> nova.compute.manager.ComputeManager.build_and_run_instance -> _do_build_and_run_instance -> _build_and_run_instance -> ova.virt.libvirt.driver.LibvirtDriver.spawn
      else:
          nova.conductor.api.ComputeTaskAPI.schedule_and_build_instances -> nova.conductor.rpcapi.ComputeTaskAPI.schedule_and_build_instances

      ```
      - server status & actions
      - aggregates & availability_zone
      - nova-cell
    - neutron
    ```text
    server - plugin - extension - agent

    https://docs.openstack.org/neutron/latest/admin/config-ml2.html#ml2-driver-support-matrix
    ```
    - cinder
    - swift
  - Ceph
  - 大数据 & AI

## 求职意向

> 我能做什么，想做什么？

说来惭愧，我从未完整开发过一个产品。
我总是试图探究编程的本质，学习那些通用的技术。
在这个过程中我必须把持一个度，既不能因为学习得太底层而导致放弃，又不能仅仅停留在使用和整合技术的层面。
技术都是不断更迭的，唯有问题以及解决问题的思想永存。

我从2014年（大二下）开始选择了 Python，至今仍是我的主力语言。对于 Python，我最大的收获就是爱上了阅读源码，同时也“不幸”染上了代码洁癖。
喜欢并能够通过阅读源码分析解决问题是我在编程上学习能力的根本。
对于编程语言，一端是 C，另一端是 Lisp，在这之间我建议 Python 和 Scala。

我并没有拿 Python 干什么实事，除了早期尝试过 Web 以外。
直到我遇到 OpenStack，开启了分布式之旅。

目前对 DataScience 也很感兴趣。

以上便是我的编程之路。

云计算是一个非常有挑战和前景的领域，它既要求扎实全面的计算机基础知识，同时又要求极高的编程功底和基础运维能力，作为 IaaS，它掌管全部 IT 基础设施并为其上的大规模应用提供高效稳定的运行环境。
云计算和 AI 就是运维的未来，也是整个 IT 业未来发展的必然趋势。
所以这个坑，我义无反顾的往下跳了。。

## 自我评价

除了颜值和不怎么会聊天以外，我是一个随和包容、诚信正直、守时、有责任心、善于规划和学习的人。
我期待一个公正且有领导力的上级以及能够精诚合作的团队，为我们共同的目标，不懈奋斗！
