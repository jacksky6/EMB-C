# AFC Configuration

[中文](README_CN.md)

These examples follow the EMB-C configuration in [AFC PR #925][afc-pr]. The installer
selection is `EMU`, board `EMB_C`, with 2 to 5 lanes.

1. Select the directory matching the number of lanes.
2. Select `With-Front-Button-PCB` for the EMU Front Button PCB, or
   `Without-Front-Button-PCB` for ordinary microswitches.
3. Set the CAN UUID in `AFC_EMU_1.cfg`, or use its commented serial connection option.
4. Copy the files to these locations relative to your Klipper configuration directory:

| Source | Destination |
| --- | --- |
| `AFC_EMU_1.cfg` | `AFC/AFC_EMU_1.cfg` |
| `EMU_1.cfg` | `AFC/mcu/EMU_1.cfg` |

5. Check the AFC includes and restart Klipper. Calibrate distances and motor currents before use.
   Back up existing files before replacing them. Do not load both variants.

With the Front Button PCB, each GRBW chain has 5 LEDs, using indexes `1-4` and `5`;
buttons use `^!`. Without it, each chain has 2 LEDs, using indexes `1` and `2`;
ordinary microswitch buttons retain `^`.

Temperature/humidity configuration is separate. Install the [TCA9548A add-on][tca]
and use its wizard to generate a configuration for AFC and your lane count.

[afc-pr]: https://github.com/AFCProject/AFC-Klipper-Add-On/pull/925
[tca]: https://github.com/jacksky6/TCA9548A-klipper-addon
