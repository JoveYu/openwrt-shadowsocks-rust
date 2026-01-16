# luci-app-shadowsocks-rust

Modern LuCI application for Shadowsocks Rust with JavaScript + ubus architecture.

## Features

- **Modern Architecture**: Uses JavaScript frontend with ubus RPC backend
- **Service Overview**: Real-time status monitoring and service control
- **Server Management**: Easy configuration of multiple shadowsocks servers
- **Local Services**: Support for SOCKS5, HTTP, Redirect, Tunnel, DNS, and TUN protocols
- **Routing Rules**: Advanced traffic routing with nftables integration
- **ACL Support**: Proper permission management

## Structure

```
luci-app-shadowsocks-rust/
├── Makefile                                    # OpenWrt package build file
├── htdocs/
│   └── luci-static/
│       └── resources/
│           └── view/
│               └── shadowsocks-rust/
│                   ├── overview.js            # Service overview and control
│                   ├── servers.js             # Server configuration
│                   ├── locals.js              # Local services configuration
│                   └── rules.js               # Routing rules configuration
└── root/
    └── usr/
        ├── share/
        │   ├── luci/
        │   │   └── menu.d/
        │   │       └── luci-app-shadowsocks-rust.json   # Menu configuration
        │   └── rpcd/
        │       └── acl.d/
        │           └── luci-app-shadowsocks-rust.json   # Access control
        └── libexec/
            └── rpcd/
                └── luci.shadowsocks-rust      # ubus RPC backend (ucode)
```

## Installation

1. Copy this directory to your OpenWrt buildroot: `feeds/luci/applications/`
2. Run `make menuconfig` and select: `LuCI -> Applications -> luci-app-shadowsocks-rust`
3. Build: `make package/feeds/luci/luci-app-shadowsocks-rust/compile V=s`
4. Install the generated ipk file on your router

## Dependencies

- shadowsocks-rust
- ucode
- ucode-mod-fs
- ucode-mod-uci
- LuCI (luci-base)

## Usage

After installation, navigate to **Services → Shadowsocks Rust** in LuCI web interface.

### Overview Tab
- View service status
- Control service (start/stop/restart/reload)
- Monitor running instances

### Servers Tab
- Add/edit/remove shadowsocks servers
- Configure server address, port, password, and encryption method
- Plugin support for v2ray-plugin and others

### Local Services Tab
- Configure local proxy services:
  - **SOCKS5**: Standard SOCKS5 proxy
  - **HTTP**: HTTP/HTTPS proxy
  - **Redirect**: Transparent proxy (for routing rules)
  - **Tunnel**: Port forwarding tunnel
  - **DNS**: DNS proxy/forwarder
  - **TUN**: Virtual network interface

### Rules Tab
- Configure transparent proxy routing rules
- Set default policies for source/destination traffic
- Whitelist/blacklist IPs and networks
- Advanced nftables customization

## API (ubus)

The application exposes the following ubus methods under `luci.shadowsocks-rust`:

- `getStatus`: Get current service status and configuration
- `reload`: Reload service configuration
- `restart`: Restart the service
- `stop`: Stop the service
- `getEncryptionMethods`: Get list of supported encryption methods

Example:
```sh
ubus call luci.shadowsocks-rust getStatus
```

## License

GPL-3.0

## Author

Jove Yu <yushijun110@gmail.com>
