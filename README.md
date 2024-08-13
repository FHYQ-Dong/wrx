# wrx 魏如雪

一套电子书导出工具，由【采集端([chrome插件](https://github.com/ckcock/wrx/releases))】和【导出端 (https://ebook-exporter.deno.dev)】两个部分组成，支持导出 HTML 和 EPUB 两种格式。本项目为采集端，导出端暂时没有开源。

## 支持的电子书平台

- 微信读书


> [!WARNING]
> 根据部分用户的反馈，在微信读书平台使用该插件有封号风险，请酌情使用。如果有小号的，尽量用小号使用该插件。  
> 【导出端】的使用不存在风险，请放心使用。


## 安装
从 [Release 页面](https://github.com/ckcock/wrx/releases)下载最新版本的 wrx.zip 并解压，然后打开 Chrome 插件管理页面(chrome://extensions/)，如下：

![image](assets/1.png)

开启右上角的开发者模式，然后通过左上角的【Load unpacked】按钮安装这个 **wrx** 插件。


## 使用

打开微信读书阅读页面，打开目录弹框，你需要把这些红点点都点成绿色的，如下所示：

![image](assets/2.png)


## 数据导出

在阅读页面的右上角，点击【导出本书数据】按钮，即可将已缓存的数据导出(此数据是加密数据，需要使用 https://ebook-exporter.deno.dev 进行解密)。


## 插件更新

该程序由 Github Actions 自动构建，通过 schedule 每个小时执行一次检测，如果发现微读web版有更新，会自动开始新的构建并发布新版本。
当插件有新版本时，需要重新按照上面的【安装】指南进行安装。


## 数据清理

如果担心该插件缓存的数据占用太多空间，或者仅仅是想知道怎么清除这些缓存的数据，那么可以打开浏览器的控制台，按照如下操作删除 **IndexedDB** 下面的 **wrx** 数据库即可：

![image](assets/3.png)

## 常见问题

### 1. 为什么不发布到插件市场，然后自动更新？而采用这种手动更新的“笨拙”方式？
由于该插件中涉及到微信打包后的js文件，该js文件是经过混淆的，但是 chrome 的插件市场不能发布带有混淆代码的插件，所以无法发布到 chrome 的插件市场。

但是该项目通过 Github Actions 的机制定期检测微信是否发版，程序会在检测到微信网页更新后自动打包出新版本，因此如果发现插件某些功能失效，请首先确认是否有新版本，通常安装新版本即可解决。
