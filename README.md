# Secure Channel

Secure Channel 是一个基于 WebRTC 技术的安全即时通讯工具，采用端到端加密确保消息传输的安全性。

## 功能特性

- **端到端加密**: 使用 ECDH P-256 密钥交换 + AES-256-GCM 应用层加密
- **安全验证**: 支持指纹验证，防止中间人攻击
- **简单易用**: 通过6位代码快速建立连接
- **无需注册**: 直接在浏览器中使用，无需账户
- **P2P连接**: 基于 WebRTC 的点对点连接，数据不经过服务器

## 技术架构

- **信令服务器**: 使用 PeerJS 作为信令服务器
- **加密算法**: ECDH (Elliptic Curve Diffie-Hellman) + AES-256-GCM
- **传输协议**: DTLS 1.3 over ICE/STUN
- **前端技术**: HTML5, JavaScript, CSS3
- **随机数源**: window.crypto (CSPRNG)

## 工作原理

1. 每个用户生成一个临时的6位代码
2. 用户之间通过安全渠道（如面对面、电话等）共享代码
3. 一方向另一方发起连接请求
4. 两端进行密钥交换，建立加密通道
5. 所有后续消息都经过端到端加密传输

## 使用方法

1. 打开 `secure-channel.html` 文件
2. 等待生成您的6位代码
3. 将您的6位代码通过安全渠道分享给对方
4. 在"Connect to peer"输入框中输入对方的6位代码
5. 点击"ESTABLISH CONNECTION"按钮建立连接
6. 连接成功后即可开始安全聊天

## 安全说明

- 所有消息均使用端到端加密，即使是信令服务器也无法解密
- 每次会话使用新的密钥对，前向保密
- 请务必通过安全渠道验证指纹，确保通信安全

## 局限性

- 需要双方同时在线才能建立连接
- 仅支持两个用户之间的直接通信
- 需要现代浏览器支持 WebRTC 和 Web Crypto API

## 浏览器兼容性

- Chrome / Edge (最新版本)
- Firefox (最新版本)
- Safari (最新版本)

## 许可证

GNU Affero General Public License v3.0 (AGPLv3)