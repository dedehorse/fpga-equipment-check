# 基于安路 EG4S20 的实验器材核对与视听交互系统

本仓库为 FPGA 创新设计竞赛正式提交源码，包含器材介绍、八步取用核对和归还评分三个阶段，以及通过 KEY3 切换阶段的 MultiBoot 工程。

## 完整工程下载

- [下载完整正式源码 RAR（22.2 MiB）](EquipmentCheck_Formal_20261103.rar?raw=true)
- [下载单文件 Flash 镜像](EquipmentCheck_Flash.bit?raw=true)
- [源码压缩包校验记录](DELIVERY_CHECK.json)

完整源码以 RAR 形式提供。解压后包含下述 `Source/` 目录、RTL、TD 工程、约束、TF 素材、模型参数和验证说明。

源码 RAR SHA256：`91217e756792081feb58ec049215644e93f082b3d486f7b0274d50cf91fb0f8b`。
Flash 镜像 SHA256：`b01a445199e99416e28293f3ee5a6fffc6e37881617ac5aa35d6f659d44216bb`。

## 工程与使用说明

请先阅读 压缩包内的 `Source/README.md` 和 `Source/00_先读_入口与烧录.md`。

- `Source/06_linked_projects/`：推荐的三阶段联动源码，工程入口与按键见源码总说明。
- `Source/05_bitstreams/linked_release/EquipmentCheck_Flash.bit`：三个阶段打包后的单文件 Flash 镜像。
- `Source/04_tf_card/`：TF 卡图片与语音素材。
- `Source/01_step1_intro/`、`02_step2_take/`、`03_step3_return/`：独立阶段源码，位于 Source 目录中。

下载 ZIP 并解压后，先运行 `Source/prepare_projects.cmd` 更新工程路径，再用 TD 打开对应 `.al`。该工具需要 Python 3，不会编译或烧录开发板。

## 验证状态

联动版三个阶段均已由 TD 编译生成 bit，资源未超过器件限制；时序报告仍有负裕量，完整 Flash 烧录和阶段跳转实板验证待完成。构建记录和验证边界见源码目录与 linked_release 中的说明。

器材身份识别按当前源码支持范围执行；编号 1～10 模块仍只检查有无，不能宣称全部 20 件身份均可识别。三个阶段通过 FPGA 重配置切换，step3 保留独立空箱校准流程。

本仓库不授予第三方 IP 或素材超出其原有许可范围的权利。
