- # Flask安装环境

  使用虚拟环境安装Flask，可以避免包的混乱和版本的冲突，虚拟环境是Python解释器的副本，在虚拟环境中你可以安装扩展包，为每个程序单独创建的虚拟环境，可以保证程序只能访问虚拟环境中的包，而不会影响系统中安装的全局Python解释器，从而保证全局解释器的整洁。

  虚拟环境使用virtualenv创建，可以查看系统是否安装了virtualenv：

  ```shell
  $ virtualenv --version
  ```

  ## 安装虚拟环境

  ```shell
  $ sudo pip install virtualenv
  $ sudo pip install virtualenvwrapper
  ```

  ## 创建虚拟环境（需在联网状态下）

  ```shell
  $ mkvirtualenv Flask_py
  ```

  **安装完虚拟环境后，如果提示找不到mkvirtualenv命令，需配置环境变量：**

  ```shell
  # 1.创建目录用来存放虚拟环境
  mkdir
  $HOME/.virtualenvs
  
  # 2.打开~/.bashrc文件，并添加如下：
  export WORKON_HOME=$HOME/.virtualenvs
  source /usr/local/bin/virtualenvwrapper.sh
  
  # 3.运行
  source ~/.bashrc
  ```

  **进入虚拟环境**

  ```shell
  $ workon Flask_py
  ```

  **退出虚拟环境**

  如果所在环境为真实环境，会提示deactivate:未找到命令

  ```shell
  $ deactivate Flask_py
  ```

  ## 1.2.1 安装Flask

  ```shell
  指定Flask版本安装
  $ pip install flask==0.10.1
  pip freeze > requirements.txt
  ```

  Mac系统：

  ```shell
  $ easy_install flask==0.10.1
  ```

  **在ipython中测试安装是否成功**

  ```shell
  $ from flask import Flask
  ```

  