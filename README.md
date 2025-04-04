# MCP客户端应用

这是一个为AI大模型服务的MCP（model context protocol）客户端程序-MCPHOLDER，在手机上也能实现类似于claude desktop的功能。它可以将cloudflare上的云端服务汇集到一起，为AI大模型提供外部的支持。

## 功能

- **AI对话页面**：用户可以选择不同的大模型进行对话，默认使用Claude-3 Sonnet 3.7
- **MCP服务页面**：显示当前可用的MCP服务及其状态，并提供添加新服务的入口
- **MCP服务测试页面**：测试新的MCP服务连接，输入服务名称、URL、端口等信息

## 技术栈

- Flutter 3.x
- Dart 3.x
- font_awesome_flutter：用于图标展示
- google_fonts：用于字体样式

## 快速开始

1、请修改lib/config目录下的openRouterApiKey，当前程序只支持openrouter的claude sonnet 3.7
2、由于网络环境问题，我只能上传flutter的lib库，因此以下安装方式不一定可用：
1. 确保已安装Flutter环境
2. 克隆此仓库
3. 运行以下命令安装依赖：
```
flutter pub get
```
4. 运行应用：
```
flutter run
```

## 项目结构

```
lib/
  ├── main.dart              # 应用入口
  ├── screens/               # 页面
  │   ├── chat_screen.dart   # AI对话页面
  │   ├── services_screen.dart  # MCP服务页面
  │   └── test_service_screen.dart  # MCP服务测试页面
  ├── widgets/               # 可复用组件
  ├── models/                # 数据模型
  └── utils/                 # 工具函数
```

## MCP协议

Model Context Protocol (MCP) 是一种协议，允许AI模型通过外部工具和API执行操作。这使得AI助手能够执行实际任务，如发送电子邮件、查询数据或控制应用程序。

更多关于MCP协议的信息，请访问 [Cloudflare的MCP文档](https://blog.cloudflare.com/remote-model-context-protocol-servers-mcp/)。

## 演示

https://youtube.com/shorts/a98GrxVYsuY

在测试服务页面，我们先:
填入服务名称：add，
再填入cloudflare的服务URL：https://remote-mcp.yunhaisui.workers.dev/sse
端口不用填写
API秘钥随便输入，但不能为空

下面点击注册客户端获取ID
成功后点击测试连接
然后会弹出一个认证的OAUTH授权按钮，点击启动oauth授权
在新弹出的webview页面点击approve
然后App会自动识别MCP中有几个tools

这时点击MCP服务，就可以看到新增了一个加法工具

在AI对话页面中输入一个简单的加法问题，claude sonnet会自动调用mcp服务，我使用的是openrouter服务，似乎有点慢，但最终也能得到正确的结果。下周我再到cloudflare上做几个好玩的MCP服务测试一下。
