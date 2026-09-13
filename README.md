# mise 配置

基于 [mise](https://mise.jdx.dev/) 的系统与开发环境引导配置，用于在新机器上通过 `mise bootstrap` 一键完成软件安装、dotfiles 链接及系统服务配置。

## 目录结构
```text
.
├── config.toml       # 通用 mise 配置：开发工具、dotfiles、引导仓库及 shell 激活
├── config.arch.toml  # Arch Linux 配置：通过 pacman/aur 安装的软件包
├── conf.d/           # 分模块的 bootstrap 配置
│   ├── user.toml     # 用户与用户组
│   ├── greetd.toml   # greetd 登录管理器：部署配置并启用服务
│   ├── dae.toml      # dae 网络代理：部署配置并启用服务
│   └── keyd.toml     # keyd 键盘映射：部署配置并启用服务
├── greetd/
│   └── config.toml   # greetd 配置文件（安装到 /etc/greetd/config.toml）
├── dae/
│   └── config.dae    # dae 配置文件（安装到 /etc/dae/config.dae）
└── keyd/
    └── default.conf  # keyd 键盘映射（安装到 /etc/keyd/default.conf）
```

## 使用

```bash
# 应用通用配置（工具、dotfiles、服务等）
mise bootstrap

# 在 Arch Linux 上额外加载 arch 配置以安装软件包
mise -E arch bootstrap
```

