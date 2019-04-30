- # requirements文件 

  Python 项目中必须包含一个requirements.txt文件，用于记录所有依赖包及其精确的版本号，以便在新环境中进行部署操作。

  在虚拟环境使用以下命令将当前虚拟环境中的依赖包以版本号生成至文件中：

  ```shell
  $ pip freeze > requirements.txt
  ```

  > 安装或升级包后，最好更新这个文件以保证虚拟环境中的依赖包。

  需求文件的内容示例如下：

  ```ini
  alembic==0.9.2
  
  ```

  当需要创建这个虚拟环境的完全副本，可以创建一个新的虚拟环境，并在其上运行以下命令：

  ```shell
  $ pip install -r requirements.txt
  ```

  