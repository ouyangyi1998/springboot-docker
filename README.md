# springboot利用docker构造镜像
- docker images 列出本机上的镜像/docker rmi -f 镜像id 删除镜像/docker ps -a 列出本机所有容器
- docker镜像和容器，容器是镜像实例化而来，容器类似虚拟机
- 本项目通过导入docker-maven-plugin 实现镜像生成
   - imageName 镜像名称 dockerDirectory dockerfile位置 
   - include 项目build之后的jar包名称（要在后面加上.jar）
   - 执行mvn命令 mvn clean package docker：build
- dockerfile操作生成docker镜像
   - from 注入项目需要的依赖（指定基础镜像）
   - volume 在镜像中创建一个挂载点
   - env 为镜像需要的环境变量
   - run 指定docker build过程中运行的程序
   - entrypoint 为容器指定默认运行程序

