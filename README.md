# kernel_xiaomi_raphael

红米 K20 Pro（raphael）内核源码，适配 HyperOS 3.0。

## 版本信息

| 项目 | 详情 |
|------|------|
| 内核版本 | 4.14.357 |
| 本地标识 | Zundamon-v4.0-rc3-LXC |
| 完整版本 | `4.14.357-Zundamon-v4.0-rc3-LXC` |
| 上游来源 | [HeliumStudio-Dev/kernel_xiaomi_raphael](https://github.com/HeliumStudio-Dev/kernel_xiaomi_raphael) |
| ELTS 基线 | OpenELA 4.14.356 |
| 编译工具链 | Clang 14.0.6 |
| 设备平台 | SM8150（骁龙855） |

## 适配 ROM

- HyperOS 3.0 `3.0.303.0.WPKCNXM`（KameYuki）

## 已开启特性

- LXC / Docker 容器支持
- KernelSU
- EROFS（系统分区）
- F2FS 压缩（LZ4 / LZO / LZORLE / ZSTD）
- eBPF / BinderFS（Android 14+）
- Incremental FS / FS Verity
- Retrofit 动态分区
- KCAL 屏幕调色
- NTFS / exFAT 读写
- OverlayFS

## 编译

工作流：[LXC-DOCKER-KernelSU_for_k20pro](https://github.com/3032252626/LXC-DOCKER-KernelSU_for_k20pro)

```bash
# 手动编译
export ARCH=arm64
export SUBARCH=arm64
make O=out raphael_defconfig
make O=out -j$(nproc)
```

## 刷入方式

产物为 AnyKernel3 格式 ZIP，可通过 TWRP / OrangeFox Recovery 或 Kernel Flasher App 刷入。

## 最近更新

- 2026-08-01: 版本 bump 至 4.14.357，对齐 ROM 内核版本，去除 openela-rc1 后缀
