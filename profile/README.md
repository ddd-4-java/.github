# DDD-4-Java

<p align="center">
  <img alt="DDD-4-Java" src="./assets/banner.svg" width="800">
</p>

<p align="center">
  <strong>面向 Java 的领域驱动设计（DDD）基础构件库 —— 让 DDD / CQRS / Event Sourcing 在 Java 生态以工程化、规范化、可复用方式落地</strong>
</p>

<p align="center">
  <a href="https://github.com/ddd-4-java"><img alt="Repos" src="https://img.shields.io/badge/Repos-TBD-blue?style=flat-square"></a>
  <a href="https://github.com/ddd-4-rust"><img alt="Rust Counterpart" src="https://img.shields.io/badge/Counterpart-ddd--4--rust-orange?style=flat-square&logo=rust"></a>
  <a href="https://github.com/partme-ai"><img alt="Ecosystem" src="https://img.shields.io/badge/Ecosystem-partme--ai-6366f1?style=flat-square"></a>
  <a href="https://github.com/ddd-4-java/.github/blob/main/profile/LICENSE"><img alt="License" src="https://img.shields.io/badge/License-Apache_2.0-green?style=flat-square"></a>
</p>

---

## 关于我们

**DDD-4-Java** 是 partme-ai 开源生态旗下的 DDD 架构基础构件组织，专注于为 Java 生态提供**领域驱动设计（DDD）/ CQRS / 事件溯源（Event Sourcing）** 的工程化基础组件。

我们的核心理念是：

> **将 DDD 方法论沉淀为可复用的代码构件，让业务架构不再"千人千面"。**

每个构件遵循统一的命名约定、接口规范与扩展点，确保跨项目、跨团队的可移植性。

### 设计原则

- **🏛️ 架构优先** — Entity / ValueObject / AggregateRoot / Repository 等核心抽象严格对齐 DDD 蓝皮书
- **🧩 可插拔** — 持久化、消息、缓存均通过 SPI 扩展，不绑定任何特定框架
- **📐 规范一致** — 与 `ddd-4-rust` 保持接口级对等，跨语言团队可对照阅读
- **🧪 测试友好** — 内置领域事件回放、聚合根快照、命令/查询一致性校验

---

## 构件矩阵

### 核心域（Domain Layer）

| 构件 | 说明 |
|------|------|
| 待发布 | `Entity`、`ValueObject`、`AggregateRoot`、`DomainEvent` |
| 待发布 | `EntityId`（强类型 ID）、`Identifier` 策略 |
| 待发布 | `Specification` 规约模式、`DomainService` 领域服务基类 |

### 应用层（Application Layer）

| 构件 | 说明 |
|------|------|
| 待发布 | `Command`、`CommandHandler`、`CommandBus` |
| 待发布 | `Query`、`QueryHandler`、`QueryBus` |
| 待发布 | `ApplicationService` 编排基类、`UseCase` 接口 |

### 基础设施层（Infrastructure Layer）

| 构件 | 说明 |
|------|------|
| 待发布 | `Repository` SPI（JPA / MyBatis-Plus / R2DBC 适配器） |
| 待发布 | `EventBus`（Spring Event / Kafka / RocketMQ） |
| 待发布 | `SnapshotStore` 聚合快照存储 |

### CQRS 与事件溯源

| 构件 | 说明 |
|------|------|
| 待发布 | `EventStore`（基于 JDBC / MongoDB） |
| 待发布 | `Saga` / `ProcessManager` 长流程编排 |
| 待发布 | `Projection` 读模型构建器 |

---

## 架构概览

```
┌─────────────────────────────────────────────────────────────┐
│                    Interfaces (REST / RPC / CLI)            │
└──────────────────────────┬──────────────────────────────────┘
                           │
┌──────────────────────────▼──────────────────────────────────┐
│                Application Layer                             │
│   Command / Query / UseCase / Saga                          │
└──────────────────────────┬──────────────────────────────────┘
                           │
┌──────────────────────────▼──────────────────────────────────┐
│                  Domain Layer                                │
│   Entity · AggregateRoot · DomainEvent · Specification       │
└──────────────────────────┬──────────────────────────────────┘
                           │
┌──────────────────────────▼──────────────────────────────────┐
│               Infrastructure Layer                           │
│   Repository · EventBus · EventStore · SnapshotStore         │
└─────────────────────────────────────────────────────────────┘
```

---

## 快速开始

> ⏳ 项目处于筹备阶段，欢迎在 [Discussions](https://github.com/orgs/ddd-4-java/discussions) 提交需求与共建提案。

### Maven 依赖（规划中）

```xml
<dependency>
    <groupId>org.ddd-4-java</groupId>
    <artifactId>ddd-core</artifactId>
    <version>0.1.0-SNAPSHOT</version>
</dependency>

<dependency>
    <groupId>org.ddd-4-java</groupId>
    <artifactId>ddd-cqrs</artifactId>
    <version>0.1.0-SNAPSHOT</version>
</dependency>
```

---

## 相关生态

| 组织 | 说明 |
|------|------|
| 🏛️ [ddd-4-rust](https://github.com/ddd-4-rust) | Rust 版本，接口级对齐 |
| 🧰 [easy-4-java](https://github.com/easy-4-java) | 业务工具集（Java） |
| 🧰 [easy-4-rust](https://github.com/easy-4-rust) | 业务工具集（Rust） |
| 💾 [rbatis-plus](https://github.com/rbatis-plus) | ORM 生态（Repository 实现层） |
| 🧠 [partme-ai](https://github.com/partme-ai) | 顶层 AI 智能体生态 |

---

## 贡献指南

欢迎贡献 DDD 基础构件！

1. **Fork** 目标仓库
2. 创建特性分支
3. 遵循既有命名约定与接口规范
4. 补充单元测试与领域示例
5. 提交 **Pull Request**

> 重大设计决策请先在 [Discussions](https://github.com/orgs/ddd-4-java/discussions) 发起 RFC。

---

## 联系我们

- Email: [partmeai@gmail.com](mailto:partmeai@gmail.com)
- GitHub: [github.com/ddd-4-java](https://github.com/ddd-4-java)

---

<div align="center">

**让 DDD 在 Java 生态工程化落地**

Made with ❤️ by PartMe AI Team

</div>