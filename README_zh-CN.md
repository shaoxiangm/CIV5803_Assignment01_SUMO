# CIV5803 SUMO baseline09

**中文** | [English](README.md)

本仓库包含为 CIV5803 电动交通规划项目开发的 SUMO baseline09。它是面向马来西亚槟城乔治市（George Town）的、已冻结的走廊级比较交通基线，不是经过完整校准的真实交通预测模型。

## 用途

baseline09 用于支持：

- 相对拥堵比较；
- 热点初筛；
- 走廊选择；以及
- 下游 EV 能耗分析。

选定的下游走廊为 C1 – Lebuh Chulia、C2 – Jalan Masjid Kapitan Keling 和 C3 – Lebuh Farquhar。下游 MATLAB EV 分析不属于本 SUMO baseline 仓库的一部分。

## 模型状态

**PASS_WITH_LIMITATIONS（通过，但存在限制）**

冻结的验证汇总位于 `outputs/baseline09_sanity_summary.csv`，记录为：加载车辆 3,640 辆；成功插入 3,526 辆（96.87%）；完成车辆 3,509 辆；仿真结束时仍有 131 辆。

## 重要限制

- 需求经过缩减和重构。
- 模型不是完整校准的 51 分区 OD 模型。
- 模拟通行量不是实测年平均日交通量（AADT）。
- baseline 不应用于绝对交通量预测。
- 结果应主要用于比较性解释。

详细说明见 `docs/assumptions_and_limitations.md`。

## 仓库结构

- `config/`：使用仓库相对路径的冻结 SUMO 配置。
- `network/`：基于 OpenStreetMap 的 SUMO 路网。
- `additional/`：边段数据输出配置。
- `demand/`：说明为何 route-demand 输入文件未随仓库发布。
- `outputs/`：冻结的验证与比较结果。
- `docs/`：限制、走廊定义和数据归属说明。

## 环境要求

本 baseline 已使用 **Eclipse SUMO 1.27.1** 检查。其他版本可能可以读取该配置，但尚未验证其能产生相同输出。

## 运行模型

首先必须在 `demand/am_baseline08.rou.xml` 放入已获授权的原始 route 文件。随后在仓库根目录执行：

`sumo -c config/am_baseline09.sumocfg`

生成的原始输出将写入 `outputs/generated/`，该目录已被 Git 忽略。

## 数据与许可

- SUMO 配置、仓库文档和处理后的结果汇总为项目编制材料。
- 路网基于 OpenStreetMap，归属与 ODbL 说明见 `docs/ATTRIBUTION.md`。
- 部分课程提供或第三方源数据未在本仓库再分发。route-demand 输入和校准输入因尚未确认公开再分发许可而被排除。

## 学术背景

本仓库包含为 CIV5803 电动交通规划项目开发的 SUMO baseline。
