## `apt-get install` 
`apt-fast` 通过使用多线程下载来给 `apt-get` 提速。
  - 添加软件源并安装

  ```bash
  $ cd ~
  $ sudo add-apt-repository ppa:apt-fast/stable
  $ sudo apt-get update
  $ sudo apt-get -y install apt-fast
  ```
  在弹出的对话框中选择 `apt-get`。
  - 使用
  
  安装完成之后使用方法和 `apt-get` 是一样的。
  ```bash
  sudo apt-fast install <software>
  ```
更多详情，请登录这个项目的 [地址](https://github.com/ilikenwf/apt-fast)。

## `pip install` 
同样存在下载缓慢的问题，通过换国内的源解决。
  - 方法 1 (一次性)
  ```bash
  pip install <package> -i https://pypi.douban.com/simple
  ```
  - 方法 2 (永久) 
  
  ```
  $ cd ~
  $ mkdir .pip
  $ cd .pip
  $ gedit pip.conf
  ```
  在`pip.conf`中写入

  ```
  [global]
  
  index-url = http://pypi.douban.com/simple
  
  [install]
  
  trusted-host=pypi.douban.com
  ```
## `git clone`
  - 打开`host`文件
  ```bash
  sudo gedit /etc/hosts
  ```
  - 修改`host`文件，添加下面命令在文档中。
  ```bash
  151.101.72.249 github.global.ssl.fastly.net
  192.30.253.112 github.com
  ```
## `wget`
`wget`的加速用`mwget`替代
  - 首先安装 `mwget`
  ```bash
  $ wget http://jaist.dl.sourceforge.net/project/kmphpfm/mwget/0.1/mwget_0.1.0.orig.tar.bz2
  $ tar -xjvf mwget_0.1.0.orig.tar.bz2
  ```
  - 执行`.configure`
  ```bash
  $ cd mwget_0.1.0.orig
  $ ./configure
  ```
  - 如果出现`error: C++ compiler cannot create executables` 说明没有安装c++编译器
  ```bash
  $ apt-get install gcc-c++
  ```
  - 如果出现`configure: error: Your intltool is too old.  You need intltool 0.35.0 or later.`，需要安装 0.35.0 以上的版本的`intltool`
  ```bash
  $ sudo apt-get install intltool
  ```
    
  - 最后安装

  ```bash
  $ make
  $ sudo make install
  ```
  安装完毕后，可以使用`mwget`下载。    
