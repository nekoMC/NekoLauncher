<p align="center"><img src="https://github.com/nekoMC/NekoLauncherSrc/blob/master/app/assets/images/SealCircle.png" width="150px" height="150px" alt="aventium softworks"></p>

<h1 align="center">Neko Launcher</h1>

<em><h5 align="center">沿用 <a href="https://github.com/dscalzi/HeliosLauncher">Helios</a> 布局和架构，启动器源代码来自 <a href="https://github.com/nekoMC/NekoLauncherSrc">NekoLauncherSrc</a></h5></em>

<p align="center">无需关注 Java、mod和冲突，NekoLauncher 会帮你处理这些问题。</p>

## 支持的特性

* 🔒猫服适配的账号机制
  * 与猫服账号系统直接适配，支持盗版（不推荐）、正版账号（即将推出）
  * 更多功能
* 📂预装 Java 与 MOD 
  * 预装 Java17，当然也允许自行配置
  * 预装各类生存必备 mod，如 iris 光影、小地图等，详见安装后的 mod 目录


#### 需要帮助？

* 可以在[猫服wiki](https://wiki.nekomc.fun)上获取现有信息，也可以在[Github](https://github.com/nekoMC/NekoLauncher/issues)上搜索您的问题或者提出问题

#### 如果喜欢别忘添加 ⭐

## Downloads

可以在 Github 发布页直接下载（这里会包含测试版本）：[GitHub Releases](https://github.com/nekoMC/NekoLauncher/releases)

更多下载方式准备中。。。

## 开发信息说明

下列内容仅在开发时有效

### 启动源码

**基本**

* Node.js v15+

---

**获取代码（确保有代码权限）**

```console
> git clone https://github.com/nekoMC/NekoLauncherSrc.git
> cd NekoLauncherSrc
> npm install
```

---

**启动**

```console
> npm start
```

---

**构建**

构建当前平台的发布包

```console
> npm run dist
```

构建指定平台的发布包

| Platform    | Command              |
| ----------- | -------------------- |
| Windows x64 | `npm run dist:win`   |
| macOS       | `npm run dist:mac`   |
| Linux x64   | `npm run dist:linux` |

交叉构建可能会存在问题

---

### Visual Studio Code

推荐使用 [Visual Studio Code][vscode].

将下列信息拷贝到 `.vscode/launch.json` 以方便开发使用

```JSON
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Debug Main Process",
      "type": "node",
      "request": "launch",
      "cwd": "${workspaceFolder}",
      "program": "${workspaceFolder}/node_modules/electron/cli.js",
      "args" : ["."],
      "outputCapture": "std"
    },
    {
      "name": "Debug Renderer Process",
      "type": "chrome",
      "request": "launch",
      "runtimeExecutable": "${workspaceFolder}/node_modules/.bin/electron",
      "windows": {
        "runtimeExecutable": "${workspaceFolder}/node_modules/.bin/electron.cmd"
      },
      "runtimeArgs": [
        "${workspaceFolder}/.",
        "--remote-debugging-port=9222"
      ],
      "webRoot": "${workspaceFolder}"
    }
  ]
}
```

此配置添加了两个 debug 选项

#### Debug Main Process

用于调试 `main process` 的选项。允许在 DevTools 窗口调试 `renderer process`

#### Debug Renderer Process

用于调试 `renderer process` 的选项。需要在 Chrome 上安装 `Debugger for Chrome` 扩展。

注意，**不能** 在调试时使用 debug 配置。Chromium 仅允许一个进程调试，另开一个吧。

---

### 致谢原作者

本项目基于 [HeliosLauncher](https://github.com/dscalzi/HeliosLauncher) 搭建，主要沿用原项目的界面设计和部分处理逻辑，向原作者表示感谢！

---

## Resources

* [猫服Wiki][https://wiki.nekomc.fun]
* [nekoMC][https://nekomc.fun]
* 猫服Q群: 643531871

---

### 猫服见！
