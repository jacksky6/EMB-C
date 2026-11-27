# AFC 配置

[English](README.md)

这些示例与 [AFC PR #925][afc-pr] 中的 EMB-C 配置保持一致。
安装器选择 `EMU`、主板 `EMB_C`，通道数选择 2-5。

1. 选择与实际通道数对应的目录。
2. 使用 EMU Front Button PCB 时选择 `With-Front-Button-PCB`，
   普通微动开关时选择 `Without-Front-Button-PCB`。
3. 在 `AFC_EMU_1.cfg` 中填入 CAN UUID，或使用其中注释的串口连接选项。
4. 将文件复制到以下位置，路径相对于 Klipper 配置目录：

| 源文件 | 目标位置 |
| --- | --- |
| `AFC_EMU_1.cfg` | `AFC/AFC_EMU_1.cfg` |
| `EMU_1.cfg` | `AFC/mcu/EMU_1.cfg` |

5. 检查 AFC include 后重启 Klipper，使用前校准距离和电机电流。
   替换前先备份已有文件，两种版本不要同时加载。

有灯板版本每路 GRBW 灯链为 5 颗，索引为 `1-4` 和 `5`，按钮使用 `^!`。
无灯板版本每路为 2 颗，索引为 `1` 和 `2`，普通微动按钮保留 `^`。

温湿度使用独立配置。安装 [TCA9548A 插件][tca]，
通过其向导选择 AFC 和实际通道数生成配置。

[afc-pr]: https://github.com/AFCProject/AFC-Klipper-Add-On/pull/925
[tca]: https://github.com/jacksky6/TCA9548A-klipper-addon
