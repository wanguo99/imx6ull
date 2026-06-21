# imx6ull

IMX6ULL development workspace aggregator repository. This repository tracks board documents and the main source trees as Git submodules.

## Clone and Initialize

```bash
git clone git@github.com:wanguo99/imx6ull.git
cd imx6ull
git submodule update --init --recursive
```

## Update Submodules

If `.gitmodules` was changed, sync the configured submodule URLs first:

```bash
git submodule sync --recursive
```

Update all submodules to the commits recorded by the superproject:

```bash
git submodule update --init --recursive
```

Update all submodules to the latest commits on their tracked remote branches:

```bash
git submodule update --init --remote --recursive
```

After a remote update, review and commit the updated submodule pointers from the repository root:

```bash
git status
git add .
git commit -m "chore: update submodules"
```

## Contents

- `buildroot/` Buildroot source tree
- `buildroot-external-tree/` external Buildroot layer for board-specific integration
- `linux-6.12/` Linux kernel source tree
- `u-boot-v2024.10/` U-Boot source tree
- `lpf/` project-specific code
- `docs/` board reference manuals, datasheets, and schematic PDFs
