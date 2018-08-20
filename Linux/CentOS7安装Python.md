# Centos 7 安装 Python

1. `yum-builddep python`
2. `wget https://www.python.org/ftp/python/3.6.6/Python-3.6.6.tar.xz`
3. `xz -d Python-3.6.6.tar.xz`
4. `tar -xf Python-3.6.6.tar`
5. `cd Python-3.6.6`
6. `./configure && make && make install`
7. `python3 -V`
8. `pip3 -V`

   ***

   如果上两条不工作：\
   `whereis python3`
   `ln -s $? /usr/local/bin/python3`[^n]
   优先将 Python 安装文件夹添加到环境变量中：

   1. 用于当前终端（临时）:\
      `export PATH=$PATH:<你的要加入的路径>`
   2. 用于当前用户：\
      `~/.bashrc` > `export PATH=<路径1>:<路径2>:$PATH`\
      `source ~/.bashrc`
   3. 用于所有用户：\
      `/etc/profile` > `export PATH=<路径1>:<路径2>:$PATH`\
      `source /etc/profile`
   4. 不推荐的方法：\
      `ln -s $? /usr/local/bin/pip`

   ***

9. Done

[^n]: $? 本意为上一条命令的状态，这里指代上一个命令的结果
