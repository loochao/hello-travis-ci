# hello-travis-ci  

Travis CI 教程，主要介绍如何使用Travis CI的检验代码功能和Code Review功能. 

A tutorial of Travis CI mainly introduces how to use Travis CI's checking code function and Code Review function.

## 目录

* [1. 检验代码](#1-检验代码)
    * [1.1 注册Travis-CI](#11-注册Travis-CI)
    * [1.2 配置Travis-CI](#12-配置Travis-CI)
    * [1.3 查看Travis-CI编译效果](#13-查看Travis-CI编译效果)
* [2. Code Review](#2-Code-Review)
* [3. 总结](#3-总结)        

                                                                                                            
## 1. 检验代码

### 1.1 注册Travis-CI

在GitHub的marketplace中搜索Travis CI，然后下载，并关联自己的GitHub账号

ps: Travis CI只支持在GitHub使用

![register.png](https://github.com/liumapp/hello-travis-ci/blob/master/data/pic/register.png?raw=true)

### 1.2 配置Travis-CI

老版本的Travis CI需要登陆它的官网：https://travis-ci.com 选中项目来开启，但是通过GitHub的marketplace关联后，是默认支持所有项目，所以不再需要走这一步

直接在项目中创建一个".travis.yml"文件

添加以下内容:

````yml
language: java
install: true
script: gradle build
jdk: oraclejdk8
````

在Java项目中，我们常用的依赖管理工具就是Maven和Gradle，Travis CI默认是Maven3进行编译，所以当我们的项目使用Gradle的时候，需要配置它的script去使用Gradle

ps: gradlew是Gradle在Linux环境下的可执行脚本文件

### 1.3 查看Travis-CI编译效果

走到这一步后，我们每一次提交代码，都会触发Travis CI去检验代码的事件

登陆Travis CI的官网，找到我们的hello-travis-ci项目，就能够直观的查看每一次编译结果：

![list.png](https://github.com/liumapp/hello-travis-ci/blob/master/data/pic/list.png?raw=true)

如果编译失败的话，点击进去也可以查看具体问题出现在哪儿（travis ci自己会提供编译环境）

![detail.png](https://github.com/liumapp/hello-travis-ci/blob/master/data/pic/detail.png?raw=true)

## 2. Code Review

通过Travis-CI是可以实现Code Review的

要做code review，肯定是在两个人以上的团队作业形式才能开展

参与方通过Fork项目后，发起PR，然后项目维护方负责对PR进行 code review，并指定由哪一个具体的人员进行code review

在参与方发起pr后的流程如下所示：

* 选择review负责人，如下图所示：

    ![choice_reviewer.png](https://github.com/liumapp/hello-travis-ci/blob/master/data/pic/choice_reviewer.png?raw=true)

* 选择完成后，该review负责人登录GitHub，将会查看到提示执行code review的信息，如下图所示：

    ![add_review.png](https://github.com/liumapp/hello-travis-ci/blob/master/data/pic/add_review.png?raw=true)

* review负责人审核代码，然后签署审核意见，常用的操作就是留下审核意见，并执行同意合并或者拒绝合并，如下图所示：

    ![review_detail.png](https://github.com/liumapp/hello-travis-ci/blob/master/data/pic/review_detail.png?raw=true)

* review负责人的审核结果，项目团队可以查看具体的审核结果（当然也包括了travis-ci的编译测试结果），如下所示：

    ![check_review.png](https://github.com/liumapp/hello-travis-ci/blob/master/data/pic/check_review.png?raw=true)

    以及
    
    ![review_result.png](https://github.com/liumapp/hello-travis-ci/blob/master/data/pic/review_result.png?raw=true)    
    
## 3. 总结

如果您已经看到这里了，就给我一个star吧，让我有动力继续更新和编写更多的教程














 
