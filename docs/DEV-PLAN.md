# DEV-PLAN · vhl-workbench

模式：无人值守夜间（2026-11-08 23:00 → 11-09 08:00）。默认值落 DEV-REQUIREMENTS §五。

## 领取记录
- 病种：Von Hippel-Lindau 综合征（罕见病 #83 · R2 · T2 · 🔥 优先招募）。
- 选择理由：BACKLOG 中 T0/T1 🔥 项（白塞 #56、软骨发育不全 #60、大动脉炎 #59、AATD #58、TTP #57 等）均已被认领；未认领 🔥 中 VHL 随访天然结构化程度最高（器官筛查矩阵）、与已有 64 仓差异化明显（遗传性多器官综合征，非单瘤种非血管炎非儿童线）；原发性免疫缺陷病与 Rett 的招募对象以患儿家长/临床为主，Rett 另有儿童线家长主体约束。认领 Issue #66，claimed 已确认（assignee samqin123）。
- 仓：https://github.com/xyb-openharness-dsh-plugins/vhl-workbench（私有），init 完成（221 文件，CLI 1.10.0-rc.25）。

## 参考基准
- 移植样板（客户端链路底本）：cervical-workbench（最近已过 V1 同形仓）。
- 成熟对比基准：breast-cancer-workbench（26 号口径）；结构对照 aml-workbench v0.2。

## 时间盒计划
M0 骨架 → M1 调研+G1 → M2 原型+G2 → M3 数据+G3 → M4 临床库 → M5 开发版+V1 → M6 装机+V2/V3 → M7 发布（冻结）→ M8 回填（冻结）→ M9 回流+晨审报告。
规则：时间盒到期停止开新里程碑；额度/鉴权错误同处最多重试 2 次即停跑写报告。

## 已知缺口（开工即声明）
- 宿主规范站 dshdesktop.com 不可达（ETIMEDOUT）→ 未核对最新规范，按 starter 内 docs/02-DSH-CONTRACT.md 执行。
- MinerU 未接入（D4）；患者资料目录未指定（D5）；0 访谈 0 临床审核（D7）。
