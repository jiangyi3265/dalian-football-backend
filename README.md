# 大连足球后端服务

为大连足球管理后台和用户端提供统一 API、身份认证、权限控制及赛事业务基础能力。

## 项目简介

本仓库是大连足球系统的 Java 后端，基于若依前后端分离版整理。当前 Maven 聚合工程提供登录验证码、JWT 鉴权、用户与角色、部门岗位、菜单和数据权限、字典参数、通知公告、操作日志、在线用户、缓存与服务器监控等通用能力，为赛事报名、赛程数据、媒体内容及多端业务接入提供服务端基础。

默认构建包含 `ruoyi-admin`、`ruoyi-framework`、`ruoyi-system` 和 `ruoyi-common`。`ruoyi-quartz` 与 `ruoyi-generator` 源码保留在仓库中，但未加入当前根 POM 的默认模块列表。

## 技术栈

- Java 8
- Spring Boot 2.5.15、Spring Framework、Spring Security
- JWT、Redis
- MyBatis、PageHelper
- MySQL、Druid 连接池
- Springfox / Swagger
- Maven 多模块工程
- Apache POI、Fastjson2、Velocity

## 关联仓库

| 项目 | 说明 | GitHub |
| --- | --- | --- |
| dalian-football-backend | 后端服务 | [dalian-football-backend](https://github.com/jiangyi3265/dalian-football-backend) |
| dalian-football-admin | 管理后台 | [dalian-football-admin](https://github.com/jiangyi3265/dalian-football-admin) |
| dalian-football-app | 用户端 | [dalian-football-app](https://github.com/jiangyi3265/dalian-football-app) |

## 快速启动

### 环境要求

- JDK 8
- Maven 3.6+
- MySQL 5.7+ 或 8.x
- Redis

### 初始化与运行

1. 在 MySQL 中创建业务数据库，并导入 [`sql/ry_20250522.sql`](sql/ry_20250522.sql)。
2. 按本地环境设置下列变量：

| 环境变量 | 用途 |
| --- | --- |
| `DB_URL` | MySQL JDBC 连接地址 |
| `DB_USERNAME` | 数据库用户名 |
| `DB_PASSWORD` | 数据库密码 |
| `REDIS_HOST`、`REDIS_PORT`、`REDIS_PASSWORD` | Redis 连接信息 |
| `TOKEN_SECRET` | JWT 签名密钥 |
| `RUOYI_PROFILE` | 上传文件与运行数据目录 |
| `DRUID_MONITOR_USERNAME`、`DRUID_MONITOR_PASSWORD` | Druid 监控登录凭据 |

3. 构建并启动：

```bash
mvn clean package -DskipTests
java -jar ruoyi-admin/target/ruoyi-admin.jar
```

默认服务端口及其他非敏感配置位于 `ruoyi-admin/src/main/resources/application.yml`。请勿把本地密码或生产配置写回仓库。

## 项目结构

```text
.
├── ruoyi-admin/       # Spring Boot 启动模块与 Web API
├── ruoyi-framework/   # 安全、权限、Web 与基础框架配置
├── ruoyi-system/      # 用户、角色、菜单、部门等系统服务
├── ruoyi-common/      # 公共模型、工具、注解与通用能力
├── ruoyi-quartz/      # 定时任务模块源码（默认构建未启用）
├── ruoyi-generator/   # 代码生成模块源码（默认构建未启用）
├── sql/               # 数据库初始化脚本
└── pom.xml            # Maven 聚合与依赖版本管理
```

## 简历描述示例

参与大连足球系统后端服务建设，基于 Spring Boot、Spring Security、JWT、MyBatis、MySQL 与 Redis 搭建统一认证、权限及基础业务 API，为赛事管理后台和多端用户应用提供一致的数据与服务能力。
