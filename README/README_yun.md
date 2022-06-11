### 零、环境准备

centos7云服务准备：https://developer.aliyun.com/adc/student/

环境准备：https://www.cnblogs.com/Lin1031/p/14187135.html

博客园地址：https://www.cnblogs.com/Lin1031/p/14187137.html


### 一、在根目录下新建一个py文件

```
cd
touch tianbiao.py
vim tianbiao.py
```

### 二、编辑python程序(注意，要修改path地址为本地，driverchrome路径)


#### 开源不易，希望GitHub给个star

#### GitHub地址：https://github.com/Lin1031/izhicheng


### 三、在根目录下创建一个脚本

```
cd 
touch my.sh
vim my.sh
```

### 四、编辑脚本内容（路径修改为本地py文件路径，学号处修改为自己的学号）

```
#!/bin/bash
. /etc/profile
. ~/.bash_profile
python的绝对路径 /root/tianbiao.py 学号 省份 市 区（主要要和i至诚上面一模一样）
```

![](https://img2020.cnblogs.com/blog/1535189/202101/1535189-20210126182455451-1926330943.png)

```
whereis python3
```

![](https://img2020.cnblogs.com/blog/1535189/202012/1535189-20201225110258857-1147785979.png)

### 五、编辑python自启动

```
sudo vim /etc/crontab
```

![](https://img2020.cnblogs.com/blog/1535189/202012/1535189-20201225024612136-319055669.png)

```
crontab -e
```

crontab可能不能运行，因此在这里再次添加定时
![](https://img2020.cnblogs.com/blog/1535189/202012/1535189-20201225110424469-118105501.png)


### 六、修改my.sh的权限为777

```
cd 
sudo chmod -R 777 /root/my.sh
```

### 七、发送错误日志到邮箱

Centos7发错错误日志到邮箱：https://www.cnblogs.com/Lin1031/p/14401289.html#/c/subject/p/14401289.html
配置好环境之后，使用 empty.sh 脚本，在 shell 里设置自动启动的时间，如果之前的填报脚本出现错误日志，则会发送邮件。
注意：使用时，需要将 tiaobiao.py 最后一行输出注释掉。一般自动启动时间建议在设置自动填报时间之后的一小时。

### 八、批量填报

编写一个 sno.txt 文件，其内容为学号 省 市 区，使用 my.sh 脚本，进行批量读文件。
注意：sno.txt 中 学号为一行一个人，最后一行不能有空行。若使用批量填报，则定时则设置为该脚本。