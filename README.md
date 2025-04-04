# MCP客户端应用

这是一个基于Flutter的MCP（Model Context Protocol）客户端应用原型，用于演示AI模型如何通过外部工具和API执行操作。

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

该应用是一个MVP（最小可行产品），可以尝试连接 https://remote-mcp.yunhaisui.workers.dev/sse 进行测试。 