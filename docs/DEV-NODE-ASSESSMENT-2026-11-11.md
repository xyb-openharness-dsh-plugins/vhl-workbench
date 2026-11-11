# 开发节点评估（2026-11-11）

## 一、实测结论

| 层 | 状态 | 证据 |
| --- | --- | --- |
| 交互原型 | **未开始** | 无 `prototypes/` 目录 |
| 装机业务界面 `public/` | **未实现** | 不存在 |
| 静态 UI 路由 | **未实现** | `dsh/index.js` 只有健康接口 |
| 面板外壳 | **骨架** | `lib/client.js` 5.0 KB，只有连接检查与「业务功能待按 spec 实现」 |
| 原生 AI 对话面板 | **未实现** | 无 `newSession` / `subscribe` / `conversation` 挂载点 |
| 实机验证 | **未验证** | 未装机 |

一句话：**本仓停在脚手架 init 之后，业务开发（M2 原型起）尚未开始。**

## 二、补齐顺序

1. **G1 需求审核**：先按 `skills/hvt-requirement-review/` 沿十条疾病轴推导 VHL 特有场景（多器官病灶分轨随访：肾/肾上腺/胰腺/视网膜/中枢；家系筛查与代记；年度筛查节奏）。B 级未清零不写业务代码。
2. **M2 原型**：交付可在浏览器双击打开的 `prototypes/v0.2/index.html`，必须含顶栏「?」整页四段疾病概要（`#disease-primer`，四段 id = definition / evidence / landscape / trend）+ 双档案切换；探针必须指向本仓原型（`probe-disease-primer.mjs --url ...`，裸跑会退出 2）。
3. **M5 移植**：`scripts/build-public.mjs` 生成 `public/`（含 primer 三件套），只替换版本字面量。
4. **静态路由 + 面板 + 会话契约 9 条**：与 behcet 同一条流水线（可参照 `aosd-workbench` / `sarcoma-workbench` 已落地的骨架）。
5. **闸门与装机**：`check-agent-pane-contract` / `build-public --check` / `build-version --check` / 单测入链；本仓同样缺文案红线检查器。
6. **实机走查**：装机后逐条点，别用静态检查冒充运行证据。

## 三、注意

- VHL 是多器官、终身随访、家系可代记的场景，**不要照搬单癌种的分期-线序结构**；重点在「同一日期多器官筛查并列」与「代记人与本人的来源区分」。
- 本仓目前没有任何原型可对照，做之前别拿别家仓的原型当基准写进交付说明。
