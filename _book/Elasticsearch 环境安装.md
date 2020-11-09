# Elasticsearch 环境安装

Elasticsearch 环境只在为新服务器首次搭建运行环境时需要，在之后的部署任务中就不在需要重复搭建了。



#### 离线安装步骤

1. 下载 Elasticsearch 离线安装包

   1. 登录 coding

   2. 浏览器访问 https://chaozhou.coding.net/p/es.bfh.zdbx.net/artifacts/98944/generic/package/139386/version/list

   3. 找到最新版本，点击下载按钮

   4. 终端下载命令(需要提供coding的用户名和密码，替换命令中 username:password 部分)

      ``` bash
      curl -L -u username:password "https://chaozhou-generic.pkg.coding.net/es.bfh.zdbx.net/node-es-serve-tar/docker-elastic-7.6.2.tar.gz?version=latest" -o docker-elastic-7.6.2-latest.tar.gz
      ```

2. 将压缩包通过移动存储设备(U盘) 拷贝至需要离线部署的服务器

3. 解压压缩包，解压缩完成后会在当前目录生成一个 elasticsearch 目录

   ``` bash
   # 使用 tar 命令解压缩
   
   tar -zxvf  docker-elastic-7.6.2-latest.tar.gz
   ```

4. 进入 elasticsearch 目录并执行其中install.sh文件

   ``` bash
   cd ./elasticsearch & ./install.sh
   ```

5. 如终端成功显示`完成`则服务安装完成。

6. 测试服务是否正常运行

   ``` bash
   curl http://localhost:9200
   
   # 如服务器运行正常，则应该返回如下内容
   # {
   #   "name" : "bfh-es01",
   #   "cluster_name" : "es-docker-cluster",
   #   "cluster_uuid" : "85ZShaViQCuUKrBq5RqgbQ",
   #   "version" : {
   #   "number" : "7.6.2",
   #    "build_flavor" : "default",
   #    "build_type" : "docker",
   #    "build_hash" : "ef48eb35cf30adf4db14086e8aabd07ef6fb113f",
   #    "build_date" : "2020-03-26T06:34:37.794943Z",
   #    "build_snapshot" : false,
   #    "lucene_version" : "8.4.0",
   #    "minimum_wire_compatibility_version" : "6.8.0",
   #    "minimum_index_compatibility_version" : "6.0.0-beta1"
   # 	 },
   #  "tagline" : "You Know, for Search"
   # }
   ```

7. 如果服务未正常启动，请查看服务运行日志

   ```bash
   # 在 elasticsearch 目录下运行
   docker-compose logs
   ```

8. 将日志信息发送给运维人员检查



# Nodejs 搜索服务离线部署



#### 离线部署步骤

1. 下载最新版本的代码服务镜像

   1. 浏览器打开 https://chaozhou.coding.net/p/es.bfh.zdbx.net/artifacts/98944/generic/package/145895/version/list
   2. 找到最新版本的文件(一般是第一个)
   3. 下载到本地

2. 将本间通过移动存储设备(U盘)拷贝至待离线部署的服务器中

3. 解压缩文件，解压缩后会在当前目录生成一个 deploy 文件夹

   ``` bash
   # 使用 tar 命令解压缩， 注意命令中文件名是你下载的文件名
   tar -zxvf deploy-es-app-stable-v1.0.0.tar.gz
   ```

4. 进入到 deploy 文件夹中并执行 install.sh 文件

   ``` bash	
   cd deploy && ./install.sh
   ```

5. 如终端正确的显示了 `done` 则服务部署成功

6. 使用浏览器测试服务是否成功，是否为最新版本

