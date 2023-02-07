# WireGuard Admin App
**Turn a Raspberry Pi into a simple WireGuard&trade; VPN Appliance**

WGAdmin is a free tool that converts a Raspberry Pi single-board computer into an easy-to-use WireGuard VPN Appliance. WGAdmin allows you to create, configure, and manage a simple WireGuard network without messing around with configuration files.

Architecturally, WGAdmin is a configuration management layer wrapped around the standard WireGuard software. It's the missing WireGuard GUI and config generator. Security and heavy lifting is handled by WireGuard natively.

## Debian Based Installation (Debian, Ubuntu, Mint, etc)

WGAdmin is available prepackaged as `.deb` files below. 
- [Debian ARM 64bit](https://dist.2ho.ca/dist/wgadmin/wgadmin_0.1.1_arm64.deb)
- [Debian ARM 32bit](https://dist.2ho.ca/dist/wgadmin/wgadmin_0.1.1_armhf.deb)
- [Debian AMD 64bit](https://dist.2ho.ca/dist/wgadmin/wgadmin_0.1.1_amd64.deb)

The packages are very simple and it can also be installed manually if you prefer.

## Generic Linux Installation

To install on other distributions... 

Be sure the dependancies are satisfied.
- Requires a recent kernel with WireGuard included (5.6+)
- or WireGuard installed separately (`apt install wireguard` etc.)
- optionally install `wireguard-tools`

