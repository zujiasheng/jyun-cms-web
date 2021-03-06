# JYunCMS 前端程序

> 更多项目介绍与指南，参见 [JYunCMS 手册](https://github.com/JYunCMS/jyun-cms-doc/blob/master/README.md)

![jyun-cms-web-new-article](https://github.com/JYunCMS/jyun-cms-doc/raw/master/assets/img/jyun-cms-web-new-article.gif)

## 安装部署

### 运行环境

- HTTP 服务器 （推荐：[Nginx](https://nginx.org/)）

### 工具

- node 10.15.x+
- npm 6.x.x+

### 准备编译环境

> 如果你的电脑里没有 Node.js 和 npm，请先安装 [它们](https://nodejs.org/en/download/)
>
> 请先在终端窗口中运行命令 `node -v` 和 `npm -v` ，**来验证一下你正在运行 node 10.15.x 和 npm 6.x.x 以上的版本**。更老的版本可能会出现错误，更新的版本则没有问题。

然后全局安装 Angular CLI

```shell
npm install -g @angular/cli
```

> 请耐心等待，安装过程可能比较缓慢，如果因为网络问题安装失败，可配合网络代理工具或切换 mpm 软件源。
>
> 安装结束可在终端窗口中运行命令 `ng --version` **来验证一下你的 Angular ClI 是否安装成功**。

### 获取主程序

通过 Git 工具，获取源代码

```shell
git clone -b master https://github.com/JYunCMS/jyun-cms-web.git
```

从一下位置，找到 `back-end-api.ts` ，修改开头第一个变量 `hostAddress` 的值为上一章节中 JYunCMS 后端服务程序配置的主机地址及启动端口号，以此使前端程序能够正确获取后端服务数据

```shell
ls ./jyun-cms-web/src/app/config/
```

在项目根目录下，通过以下命令，编译生成待部署的前端文件，产物保存在 `dist` 文件夹下

```shell
npm install
ng build --prod
ls ./dist
```

### 运行

可将上一步编译产生的文件，部署在常见的 HTTP 服务器上，这里推荐使用 [Nginx](https://nginx.org/)

注意在（Nginx）server 配置项中，使用 `try_files` 指向 `index.html` ，解决刷新 404 的问题，更多 JYunCMS 前端程序配置说明，请参阅相关文档

## 开发指南

> 更多 **参与贡献** 说明请参阅 [JYunCMS 手册 第三章](https://github.com/JYunCMS/jyun-cms-doc/blob/master/3.1_contribution_method.md)

- 配置环境参考上方安装部署一节
- 推荐使用 [IntelliJ IDEA](https://www.jetbrains.com/idea/) 、[WebStorm](https://www.jetbrains.com/webstorm/) 或 [VSCode](https://code.visualstudio.com/) 进行编码

