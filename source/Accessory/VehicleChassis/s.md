# Sphinx
##	安装

```text
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple sphinx

sphinx-quickstart

> Separate source and build directories (y/n) [n]: y  <--------这里选y表示编译的文件单独放在build中
The project name will occur in several places in the built documentation.
> Project name: SphinxDemo     <--------这里输入项目的名称
> Author name(s): xxpcb        <--------这里输入作者
> Project release []: v1.0     <--------这里输入版本号

make html

pip install -i https://pypi.tuna.tsinghua.edu.cn/simple sphinx-autobuild
sphinx-autobuild source build/html

// 更改主题 下载
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple sphinx_rtd_theme
// 修改conf.py 文件 html_theme = 'sphinx_rtd_theme'


// 安装markdown工具
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple recommonmark
// 使用markdown的表格
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple sphinx_markdown_tables
// 修改conf.py 文件 extensions = ['recommonmark','sphinx_markdown_tables']
```

##	教程

* 本地启动输入：```sphinx-autobuild source build/html```
* 一级目录文件：```source/index.rst```

```
Welcome to hiwonder-docs's documentation!
=========================================

.. toctree::
   :maxdepth: 2  //表示插入所有这些文档的目录，最大深度为2，即一个嵌套标题。
   :caption: Robot Kit  //

   Robot_kit/RaspberryPi/index


.. toctree::
   :maxdepth: 1
   :caption: Accessory

   Accessory/VehicleChassis/index

```

* 目录树格式如图

![49f63d4206588525cf457eff55607990](.\49f63d4206588525cf457eff55607990.png#pic_left)





##	上传	

![dd1314d37393ad2c29a9fd16ca30849c](.\dd1314d37393ad2c29a9fd16ca30849c.png)

### 新增目录树

**文档全部为md格式，rst格式只用来生成目录树**

`source/index.rst` 文件添加

```
.. toctree::
   :maxdepth: 2 
   :caption: Robot Kit
   
   Robot_kit/RaspberryPi/index  // 目录相对路径
```

`.. toctree::`   声明了一个树状结构

`:maxdepth: 2`   表示插入所有这些文档的目录，最大深度为2，即除读取子目录文档标题。

`:caption:`   表示目录树标题，**`source/index.rst`中添加这一配置，其他一律不添加**

####	新增一级目录

目录树下新增一级目录首先在 source/index.rst 文件目录树下添加子目录相对路径，如：

```
Robot_kit/RaspberryPi/index
.rst后缀文件无需写带后缀，.md文件要加上后缀
```

如果是rst文件，即继续嵌套目录，标题的形式是：**双下划线（或单下划线）包裹**

```
Welcome to hiwonder-docs's documentation!
=========================================
```

如果是md文件，引入文档，标题就是md文件的标题

```
# MasterPi RPi 4B Version
```

要注意需要嵌套目录的情况，Robot_kit/RaspberryPi/MasterPi 文件夹中有多个md文档的情况





