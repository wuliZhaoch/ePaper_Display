# Ubuntu Linux 安装Deb文件的三种方法

### 方法1：使用默认软件中心
- 在Ubuntu中安装 **deb** 文件最简单的方式就是使用默认软件中心
- 双击已下载的 **deb** 文件，它会自动打开默认软件中心，点击 install 按钮并输入登陆密码即可 
- 例如：安装QQ_Music
  - 双击QQ_Music deb安装文件
    - ![Screenshot from 2021-09-05 18-09-42](/home/chenhuizhao/Desktop/Ubuntu Notes/Typora_images/Screenshot from 2021-09-05 18-09-42.png)
  - 点击 Install 按钮进行安装，以下图片是已经安装过的，正常显示会有一个Install按钮点击即可
    - ![Screenshot from 2021-09-05 18-18-07](/home/chenhuizhao/Desktop/Ubuntu Notes/Typora_images/Screenshot from 2021-09-05 18-18-07.png)

### 方法2：使用Gdebi应用程序安装Deb软件包及其依赖项

- 安装deb文件包，安装的过程中可能会出现没有依赖包的问题，软件中心处理不了没有依赖包问题

- Gdebi 是一个轻量级GUI的应用程序，它是由安装deb软件包的一个用途，它会识别依赖项，并尝试在安装.deb文件的同时安装这些依赖项

- 可以在软件中心或者使用命令来安装Gdebi：

  - ``````
    sudo apt install gdebi
    ``````

### 方法3：在命令行中使用dpkg安装.deb文件

​		在命令行中安装deb软件包，可以使用 **apt**或者 **dpkg** 命令，实际上，**apt** 命令在底层上使用 **dpkg** 命令。**apt** 更流行和易于使用

- 使用 **apt** 命令安装deb文件

  - ```
    sudo apt install Path_to_deb_file
    ```

- 使用 **dpkg** 命令安装deb文件

  - ```
    sudo dpkg -i Path_to_deb_file
    ```

- 如果在安装deb软件包的过程中出现依赖包的错误，可以使用以下命令修复依赖包

  - ```
    sudo apt install -f
    ```

- 如何移除deb软件包
  - 使用 **grep** 命令来搜索软件包

    - ```
      sudo apt list --install | grep Appname
      
      WARNING: apt does not have a stable CLI interface. Use with caution in scripts.
      Appname/now 1.2.1 amd64 [installed,local]
      ```
    - ```
      dpkg -l | grep Appname
      
      ii appgrid 0.298 all Discover and install apps for Ubuntu (ii 表示应用程序已经正常安装)
      ```
  - 使用 **apt** 命令移除deb软件包
  
    - ```
      sudo apt remove Program_name
      ```
  
  - 使用 **dpkg** 命令移除的文件包
  
    - ```
      dpkg -r Program_name
      ```

