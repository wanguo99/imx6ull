# imx6ull

IMX6ULL 开发工作区聚合仓库。这个仓库使用 Git 子模块统一管理板级文档和主要源码树。

## 克隆与初始化

```bash
git clone git@github.com:wanguo99/imx6ull.git
cd imx6ull
git submodule update --init --recursive
```

如果网络较慢，可以单独初始化较大的子模块，并使用浅克隆和部分克隆减少下载量：

```bash
git submodule update --init --depth 1 --filter=blob:none -- linux-7.0
git submodule update --init --depth 1 --filter=blob:none -- uboot-2024.10
```

如果中断导致子模块留下半截目录，先清理对应路径后重试：

```bash
rm -rf linux-7.0 .git/modules/linux-7.0
git submodule update --init --depth 1 --filter=blob:none -- linux-7.0
```

检查子模块初始化状态：

```bash
git submodule status
git status --short
```

## 更新子模块

如果修改了 `.gitmodules`，请先同步子模块 URL 配置：

```bash
git submodule sync --recursive
```

将所有子模块更新到主仓库当前记录的提交：

```bash
git submodule update --init --recursive
```

将所有子模块更新到各自跟踪远端分支的最新提交：

```bash
git submodule update --init --remote --recursive
```

如果执行了远端更新，请在仓库根目录检查并提交新的子模块指针：

```bash
git status
git add .
git commit -m "chore: update submodules"
```

## 目录说明

- `buildroot/` Buildroot 源码树
- `br2-external/` 面向板级集成的 Buildroot 外部层
- `linux-7.0/` Linux 内核源码树
- `uboot-2024.10/` U-Boot 源码树
- `lpf/` 项目自定义代码
- `docs/` 板卡参考手册、数据手册和原理图 PDF
