# OpenWrt Shadowsocks-Rust

一个针对OpenWrt的Shadowsocks Rust实现，包含LuCI Web管理界面和规则管理工具。

## 项目概述

该项目提供了一套完整的Shadowsocks Rust代理解决方案，专门为OpenWrt路由器设计，包括：

- **shadowsocks-rust**: 基于Rust的高性能Shadowsocks代理服务
- **luci-app-shadowsocks-rust**: OpenWrt LuCI Web管理界面

## 主要功能

### Shadowsocks-Rust核心
- 支持多种加密方式（AEAD-Cipher-2022等）
- 本地DNS解析 (`local-dns`)
- HTTP代理支持 (`local-http`)
- 重定向代理 (`local-redir`)
- TUN隧道模式 (`local-tun`)
- 通用隧道支持 (`local-tunnel`)

### LuCI Web界面
- 服务器配置和管理
- 规则配置与编辑
- 本地化支持（简体中文）
- 直观的管理界面

### 规则引擎
- 高级链式规则处理
- 灵活的规则集合管理
- NFT防火墙集成
