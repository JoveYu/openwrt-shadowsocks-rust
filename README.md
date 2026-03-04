# OpenWrt Shadowsocks-Rust

A Shadowsocks Rust implementation for OpenWrt, including a LuCI web management interface and rule management tools.

## Project Overview

This project provides a complete Shadowsocks Rust proxy solution designed for OpenWrt routers, including:

- **shadowsocks-rust**: A high-performance Shadowsocks proxy service written in Rust
- **luci-app-shadowsocks-rust**: An OpenWrt LuCI web management interface

## Key Features

### Shadowsocks-Rust Core
- Supports multiple encryption methods (including AEAD-Cipher-2022)
- Local DNS resolution (`local-dns`)
- HTTP proxy support (`local-http`)
- Redirect proxy mode (`local-redir`)
- TUN tunnel mode (`local-tun`)
- Generic tunnel support (`local-tunnel`)

### LuCI Web Interface
- Server configuration and management
- Rule configuration and editing
- Localization support (Simplified Chinese)
- Intuitive management interface

### Rule Engine
- Advanced chained rule processing
- Flexible rule set management
- NFT firewall integration
