# WireGuard Admin App
**Turn a Raspberry Pi into a simple WireGuard&trade; VPN Appliance**

WGAdmin is a free tool that converts a Raspberry Pi single-board computer into an easy-to-use WireGuard VPN Appliance. WGAdmin allows you to create, configure, and manage a simple WireGuard network without messing around with configuration files.

![Network Summary](./wgadmin-network.png)

Architecturally, WGAdmin is a configuration management layer wrapped around the standard WireGuard software. It's the missing WireGuard GUI and config generator. Security and heavy lifting is handled by WireGuard natively.

## Debian Based Installation (Debian, Ubuntu, Mint, etc)

WGAdmin is available prepackaged as `.deb` files below. 
- [wgadmin_0.1.1_arm64.deb](https://dist.2ho.ca/dist/wgadmin/wgadmin_0.1.1_arm64.deb) (ARM 64bit)
- [wgadmin_0.1.1_arm64.deb](https://dist.2ho.ca/dist/wgadmin/wgadmin_0.1.1_armhf.deb) (ARM 32bit)
- [wgadmin_0.1.1_arm64.deb](https://dist.2ho.ca/dist/wgadmin/wgadmin_0.1.1_amd64.deb) (AMD 64bit)

The packages are very simple and it can also be installed manually if you prefer.

## Generic Linux Installation

To install on other distributions...

Be sure the dependancies are satisfied.
- Requires a recent kernel with WireGuard included (5.6+)
- or WireGuard installed separately (`apt install wireguard` etc.)
- optionally install `wireguard-tools`

Download the appropriate `wgadmin` binary for your architecture and place is in `/usr/local/bin`
- [wgadmin](https://dist.2ho.ca/dist/wgadmin/arm64/wgadmin) (ARM 64bit)
- [wgadmin](https://dist.2ho.ca/dist/wgadmin/armhf/wgadmin) (ARM 32bit)
- [wgadmin](https://dist.2ho.ca/dist/wgadmin/amd64/wgadmin) (AMD 64bit)

Download the `wgadmin.service` file and place it in `/lib/systemd/system`
- [wgadmin.service](https://dist.2ho.ca/dist/wgadmin/wgadmin.service)

Enable and start it (as root)
```
    chown root:root /usr/local/bin/wgadmin
    chmod 755       /usr/local/bin/wgadmin
    systemctl daemon-reload
    systemctl enable wgadmin.service
    systemctl start wgadmin.service
```
    
# How it Works

WGAdmin needs to run as a daemon. WGAdmin will be responsible for starting and stopping the WireGuard tunnels. 
i.e. You do not install `wg-quick@wg0` etc. 

It is possible to use `wg-quick` for other tunnels that are separate from 
the interface managed by WGAdmin. e.g. let WGAdmin manage `wg0` and `wg-quick` manage `wg1` etc.
  
