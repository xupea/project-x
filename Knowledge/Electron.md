前提假设你是一个合格的前端开发工程师，即熟悉 Javascript 基础，浏览器基础，以及 npm 基础；熟悉任意框架无所谓



## 什么是 Electron

Electron 是一个使用 JavaScript、HTML 和 CSS 构建桌面应用程序的框架。通过在其二进制文件中嵌入 Chromium 和 Node.js，Electron 允许你维护一套 JavaScript 代码库，并创建可在 Windows、macOS 和 Linux 上运行的跨平台桌面应用程序——不需要原生开发经验。



Chromium 和 Nodejs 分别介绍

Chromium 是多进程，Nodejs 具备操作系统能力



### Chromium

Chromium 是由 Google 公司主导开发的开源 Web 浏览器，它是 Chrome（谷歌浏览器，商业化且闭源）的核心代码基础



Chromium 的核心组件包括：

Blink 渲染引擎

V8 JavaScript 引擎

多进程架构

安全沙箱

开发者工具



Chromium 页面加载顺序，开发者工具，以及优化，都是适用的



### Nodejs

Nodejs 包括 Buffer，C++ addons，Child process，Crypto，Events，File system，Stream，Net



而不是 Express Koa 等网络框架知识



例如即时通信应用，网络，本地数据库，通知，截图，音视频，



### 挑战

Nodejs 这块



## 快速入门（创建您的第一个应用程序）



不依赖任何脚手架，开始构建一个 Electron 应用

Electron 应用程序的结构与其它 Node.js 项目相同。首先创建一个文件夹并使用 `npm` 命令初始化。

```
mkdir my-electron-app && cd my-electron-app
npm init --y
```

然后安装 Electron 包到 `devDependencies`

```
npm install --save-dev electron
```



> Electron 为什么是在 devDependencies 里？
>
> devDependencies 是应用程序在生产环境下运行不需要的依赖包列表，生产上的代码肯定也会使用 Electron 的 APIs，所以把 Electron 放到 devDependencies 里的确是有点反直觉的。然而事实上打包后的应用程序会捆绑 Electron 二进制文件，所以无需指定 Electron 为生产依赖



初始化并安装 Electron 后，你的 package.json 文件应该是这样的。



```json
{
  "name": "my-electron-app",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "electron": "^30.0.2"
  }
}
```



你还应该有一个包含 Electron 可执行文件的 node_modules 文件夹，以及一个 package-lock.json，其中指定了要安装的确切依赖版本。



运行程序：

尽管我们还没有编写任何代码，但是我们还是可以运行的，在 package.json 中，将 `electron` 添加到 `scripts` 的 `start` 命令中：

```json
{
	...
  "scripts": {
  	"start": "electron",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  ...
}
```



electron 是有 Electron 提供的命令，执行 `npm start` ，你会看到一个窗口已经打开：

![electron-default-app](/Users/xupea/Desktop/Electron-Screenshots/electron-default-app.png)

同时控制台看到：

![electron-default-terminal](/Users/xupea/Desktop/Electron-Screenshots/electron-default-terminal.png)

我们需要指定 Electron 应用程序的入口文件或地址



electron 命令 



当我们不指定任何入口或参数的情况，会打开默认的（Electron 提供的）



## 进程模型

Electron 继承了 Chromium 的多进程架构，这使得 Electron 在架构上与现代网页浏览器非常相似。

所以了解 浏览器的多进程模型，有助于了解 Electron 架构



主进程

每个 Electron 应用程序都有且仅有一个主进程，作为应用程序的入口点。主进程在 Node.js 环境中运行，这意味着它能够使用 `require` 来加载模块并使用所有 Node.js 的API。



窗口管理

主进程的主要目的是使用 `BrowserWindow` 模块来创建和管理应用程序窗口。



每个 BrowserWindow 实例都会创建一个 应用窗口，加载一个网页，单独的渲染进程中

主进程通过 win.webContents 和渲染内容交互



EventEmitter



应用生命周期



Native APIs

菜单，托盘，对话框



渲染进程





## IPC

通信



渲染进程到主进程（单向通信）



渲染进程到主进程（双向通信）



主进程到渲染进程



渲染进程到渲染进程





## 最佳实践



性能 



安全



## 测试

单元测试



端到端测试



## 实战





## 签名和打包



## 更新





## ESM

https://www.electronjs.org/docs/latest/tutorial/esm
