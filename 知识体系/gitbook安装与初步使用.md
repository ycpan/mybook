# gitbook安装与初步使用测试
### 安装nvm方法：
方法一【我用的这个】： brew install nvm ， 根据提示手动添加东西到 ~/. bash_profile中，然后source ~/. bash_profile。
备注:nvm是一款管理npm版本的软件。
### 检查安装情况
```
nvm -v // nvm版本号为 0.37.2
// 选用
nvm ls // 列出本地已安装好的nodejs版本
nvm use 6 // 全局切换版本，若提示还未安装nodejs v6，则install
nvm install 6 // 或者nvm install v10.23.0
nvm current // 查看当前使用的node版本
nvm ls-remote // 远程可以安装的所有node版本号
```
gitbook build书籍的时候，推荐用node6版本，这样出来的书籍点击目录能跳转；  
安装gitbook的时候，推荐用node10版本.
```
nvm ls // 查看本地是否有node6/10版本，若无则安装，如下
nvm install 6
nvm install 10
```
检查当前安装版本
```
nvm ls
nvm current
node -v // v10.23.0
npm -v // 6.14.8
```
### 安装gitbook-cli(就是安装gitbook)
安装 gitbook-cli 【cli：命令行】
推荐用下面命令行安装，方便
```
nvm use 10 // 切换nodejs版本，方便顺利安装gitbook-cli
// npm search gitbook-cli
npm install -g gitbook-cli // -g全局，安装命令行版gitbook-cli
// npm install -g gitbook-cli@2.3.2 --save-dev //安装指定版本的命令行版gitbook-cli
gitbook -V //查看版本号，看是否安装成功
gitbook fetch 2.6.9 // 再安装2.6.9，用该版本build出来的书籍点击目录可以跳转
gitbook ls # 查看当前版本
gitbook ls-remote #查看远程有哪些gitbook版本可以安装
```
gitbook -V// 查看gitbook当前版本：
gitbook ls// 查看本机gitbook都安装了哪些版本
```
### 下载插件
npm i gitbook-plugin-summary --save   # 这个插件要在node 10的版本下下载，否则会报错。
笔记文件夹下的book.json文件，没有就自己创建一个，添加如下代码：
{ "plugins": ["summary"] }
也可以
```
npm install ./   //就可以安装book.json中的插件了
```
### 使用测试
编辑SUMMARY.md文件
```
# Summary

* [Introduction](README.md)
* [Read](Read/README1.md)
* [1. 季节](季节/ReadMe2.md)
    * [1.1 春](季节/section0.md)
    * [1.2 夏](季节/section1.md)
* [2. 城市](城市/ReadMe3.md)
    * [1.1 北京](城市/section0.md)
    * [1.2 上海](城市/section1.md)
```
### 生成目录
```
gitbook init
SUMMARY.md改动后，需要 gitbook init，生成对应的文件
```
### 发布
```
gitbook serve
```
### 导出书籍
build时用 --gitbook=2.6.7或2.6.9，对应的nodejs切换到V6，这样生成书籍点击目录可以跳转。
nvm use 6 // 对应gitbook2.6.7和2.6.9
gitbook build --gitbook=2.6.9 书籍路径 输入路径 // 解决点击目录不能跳转
//gitbook build 书籍路径 输入路径 build结束后，nvm再切换回原来版本：
```





