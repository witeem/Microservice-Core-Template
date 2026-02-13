# 微服务核心模板

基于 .NET 6 的轻量级微服务架构模板，集成服务注册发现、API网关等核心功能。

## 🚀 技术栈

- **.NET 6** - 核心框架
- **SqlSugar** - ORM 框架，支持 MySQL
- **Consul** - 服务注册与发现
- **Ocelot** - API 网关
- **RabbitMQ** - 消息队列
- **Redis** - 缓存服务
- **Scrutor** - 批量依赖注入

## 📦 项目结构

```
├── DataCon.Application/          # 应用服务层实现
├── DataCon.IApplication/         # 应用服务层接口
├── DataCon.Repositories/         # 数据仓储实现
├── DataCon.IRepositories/        # 数据仓储接口
├── DataConCore/                  # 核心组件库
│   ├── Exceptions/               # 异常处理
│   ├── Extensions/               # 扩展方法
│   ├── Handels/                  # 工具处理类
│   └── TableEntitys/             # 实体模型
├── DataConApi/                   # RESTful API 服务
├── DataConGateway/               # Ocelot API 网关
├── DataConPro/                   # MVC 客户端
└── DataConMenu/                  # 菜单服务
```

## 🔧 快速开始

### 前置要求

- .NET 6 SDK
- MySQL 数据库
- Consul 服务
- Redis 服务（可选）
- RabbitMQ 服务（可选）

### 配置说明

1. **配置数据库连接**
   - 修改各项目中的 `appsettings.json` 文件
   - 配置 MySQL 连接字符串

2. **配置 Consul**
   - 启动 Consul 服务
   - 配置服务注册地址

3. **配置 Ocelot 网关**
   - 编辑 `DataConGateway/ocelot.json`
   - 配置路由规则和服务发现

### 运行项目

```bash
# 启动 API 服务
cd DataConApi
dotnet run

# 启动网关
cd DataConGateway
dotnet run

# 启动 gRPC 服务
cd DataCon.Grpc
dotnet run

# 启动 MVC 客户端
cd DataConPro
dotnet run
```

## 📋 核心功能

### 依赖注入
- 使用 Scrutor 批量注册服务
- 支持懒加载模式（Lazy Resolution）

### 服务通信
- RESTful API
- 通过 Consul 实现服务发现

### API 网关
- Ocelot 路由转发
- 集成 Consul 服务发现
- 支持配置热更新

### 异常处理
- 全局异常过滤器
- 自定义业务异常
- 统一错误响应格式

## 🛠️ 开发工具

### 常用扩展
- 字符串扩展（StringExtensions）
- 异常扩展（ExceptionExtension）

### 工具类
- API 处理（ApiHandel）
- 加密处理（EncyptHandel）
- 模型映射（ModelMapHandel）
- SqlSugar 处理（SqlSugarHandel）

## 📝 API 文档

启动服务后访问 Swagger 文档：
- API 服务: `http://localhost:5000/swagger`
- 根据项目配置调整端口

## 🔒 健康检查

各服务均已集成健康检查端点，用于监控服务状态。

---

⭐ 如果这个项目对您有帮助，欢迎 Star！
