<img width="1438" height="1059" alt="image" src="https://github.com/user-attachments/assets/3f76f189-3e84-4841-aa9f-3dd2c904d7ed" /># Xiaomi Power Bank Console · WPB1026S Qi2.2

基于 [LOSRET/xiaomi-powerbank-console](https://github.com/LOSRET/xiaomi-powerbank-console) 扩展的 Vue 3 + TypeScript + WebHID 小米移动电源详情工具。

**已加入小米金沙江充电宝新国标 10000mAh 45W（WPB1026S）的 Qi2.2 开启与关闭功能支持。**

## 在线使用与完整源码

- **在线网站：[mipluswpb1026s.pages.dev](https://mipluswpb1026s.pages.dev/)**
- <img width="1438" height="1059" alt="J6HVK_~69{9E9{FB}5~P IA" src="https://github.com/user-attachments/assets/a067aa82-8670-4323-a663-a059037080c0" />

- **[下载完整源码包](xiaomi-powerbank-console-WPB1026S-source.zip)**
- [WPB1026S 操作与验证说明](WPB1026S_QI2.md)

本仓库以完整 ZIP 源码包交付。解压后包含 src、public、scripts、docs、自动测试、依赖锁文件及 Cloudflare Pages 配置，保留原目录结构；不包含 node_modules、登录凭据或构建缓存。打开 ZIP 文件页面后点击下载按钮即可保存。

## 功能

- 通过 WebHID 连接小米移动电源，显示型号、电量、健康度、循环次数、温度、电芯信息和异常记录。
- 保留 WPB1025S 的 Qi2.2 开关，新增 WPB1026S 加密设置协议。
- 每次设置根据当前设备和本次握手生成命令；设备确认成功且状态回读一致后才显示操作成功。
- 设备数据在浏览器本地处理；地区检测调用 country.is，不携带设备数据。

## 连接方法

1. 使用支持数据传输的 USB-C 线连接充电宝指定接口，接口位置参见网站支持型号页。
2. 在 4 秒内连续快速按 8 次充电宝按键，进入数据传输模式。
3. 使用桌面 Chrome、Edge 或 Opera 打开网站，点击“建立连接”，选择 XiaomiPowerBank。
4. 等待读取完成，确认型号为 WPB1026S，再按提示操作 Qi2.2 开关。

Firefox、Safari 以及手机浏览器不支持本工具所需的 WebHID。必须使用 HTTPS 或 localhost。


## 本地运行与部署

安装 Node.js 22+，解压源码包并进入 xiaomi-powerbank-console 文件夹：

```bash
npm ci
npm run dev
```

检查及构建：

```bash
npm run typecheck
npm test
npm run build
```

构建产物在 dist，适用于 Cloudflare Pages。当前在线网站采用直接上传部署，在 GitHub 更新源码包不会自动更新网站。若自行部署，请将 wrangler.toml、package.json 部署项目名、src/seo/site.ts 和 public/robots.txt 的地址改为自己的项目。

## 来源与许可证

- 前端基础项目：[LOSRET/xiaomi-powerbank-console](https://github.com/LOSRET/xiaomi-powerbank-console)
- Python 协议参考：[yomiel-s/xiaomi-powerbank-tools](https://github.com/yomiel-s/xiaomi-powerbank-tools)
- 详细适配来源与协议说明见源码包 docs/WPB1026S_QI2.md。

遵循 [MIT License](LICENSE)，保留原项目版权声明。本工具非小米官方产品，与小米公司无隶属关系。
