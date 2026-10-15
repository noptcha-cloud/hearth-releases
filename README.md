# Hearth 发行版

Hearth：在本机用 tmux 托管 Claude Code 进程，并在浏览器里查看与操作。

这个仓库只放发行包，不放源码。macOS / Linux 上一行安装（不用 sudo）：

```bash
curl -fsSL https://github.com/noptcha-cloud/hearth-releases/releases/latest/download/install.sh | bash
```

安装脚本会：

- 检查依赖：Node.js ≥ 22.18、tmux、git 缺了时，可以不用 sudo 装进 `~/.hearth/tools`；没有 Claude Code 时，可以用官方脚本装上
- 下载发行包并核对 sha256，装到 `~/.hearth/app`，命令是 `~/.local/bin/hearth`
- 配置认证（Claude 订阅或 API Key / 兼容端点）、自检，并可以装成常驻服务（macOS launchd / Linux systemd --user）

装好后：

```bash
hearth url        # 本机访问链接 http://127.0.0.1:7878/?token=…
hearth update     # 升级
hearth help       # 全部命令
```

服务只监听 127.0.0.1。远程访问、浏览器扩展等说明见安装后的 `~/.hearth/app/docs/DEPLOY.md`。

可选环境变量：`HEARTH_VERSION=0.1.0` 装指定版本，`HEARTH_YES=1` 无人值守安装。
