# AI店长 Skill

董逻辑 · 基于《AI店长：用AI重做门店经营》的门店经营助手

当前版本：**v0.2.0**。支持中文自然语言调用，增加单品贡献与菜单试点、短视频到订单的经营跟踪。早期版本保留在 Releases 中。

从行业、客群定位、门店规模和当前问题出发，帮助老板与店长诊断经营问题，制作具体工作材料，再根据执行结果复盘。

## 工作方式

首次使用先了解三项：开什么店、在哪里和服务谁；几家店、多少员工；现在最想解决什么问题。根据任务补充数据、目标和资源。已有档案时直接继续工作。

| 模式 | 常见需求 | 交付 |
|---|---|---|
| 经营诊断 | 不知道先改什么、销售增长却没赚到钱 | 原因假设、证据、优先动作与验证计划 |
| 营销获客 | 活动、文案、复购、口碑、短视频、SEO/GEO 内容 | 内容草稿、活动方案、承接流程与订单跟踪表 |
| 商品采购 | 选品、菜品贡献、菜单、库存、补货、供应商比较 | 单品账、菜单试点、补货建议与采购条件 |
| 人员组织 | 排班、新人培训、服务一致性 | 班表草案、带教任务与 SOP |
| 经营复盘 | 日报周报、活动或试点效果 | 同口径比较与继续、调整或停止的决定 |

一个 Skill 包含五种内部流程，无需额外安装子 Skill。

## 安装到 Codex

首次安装时，克隆仓库并将技能目录放入本机技能目录：

```bash
git clone https://github.com/DONGLUOJI/ai-store-manager-skill.git
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R ai-store-manager-skill/ai-store-manager "${CODEX_HOME:-$HOME/.codex}/skills/"
```

如果已经安装同名 Skill，请先检查本地修改，再更新安装目录。安装后在新会话中直接输入“调用 AI店长 skill”，并说明你的门店与任务。显示名称为“AI店长”，内部标识保留为 `ai-store-manager`；需要系统显式引用时仍可使用 `$ai-store-manager`。

## 使用示例

```text
调用 AI店长 skill，帮一家社区烘焙店建立经营档案。
一家店，6名员工，主要服务周边住户。
目前下午产品常卖不完，先判断应该从哪里改善。
```

```text
调用 AI店长 skill，分析这份商品销售、成本和库存表。
先解释利润为什么下降，再做一个本周可以执行的改进方案。
```

```text
调用 AI店长 skill，根据员工可用时间和分时段岗位需求排班。
排不出来的时段请列出缺口。
```

```text
调用 AI店长 skill，复盘上次会员活动。
这是活动前后订单、折扣、商品成本和渠道费用，判断值得继续还是调整。
```

```text
调用 AI店长 skill，用这家店的真实菜品和视频素材设计一条短视频。
我想看发布后从有效咨询到实际订单的变化，先给我内容和记录方案。
```

用户要求保存时，Skill 可在指定位置或当前工作区的 `ai-store-data/<store-id>/` 记录门店档案、试点和复盘。门店资料保存在本地，不属于本仓库的发布内容。

## 文件

- [Skill 入口](ai-store-manager/SKILL.md)
- [门店档案](ai-store-manager/references/intake.md)
- [工作流程](ai-store-manager/references/workflows.md)
- [指标口径](ai-store-manager/references/metrics.md)
- [单品贡献与菜单试点](ai-store-manager/references/menu-profit.md)
- [从短视频到订单](ai-store-manager/references/video-to-orders.md)
- [书稿使用说明](ai-store-manager/references/book-map.md)
- [设计说明](AI店长-Skill设计说明.md)
- [模拟试用记录](AI店长-Skill试用记录.md)
- [《AI店长》公开阅读仓库](https://github.com/DONGLUOJI/ai-store-manager-book)

## 当前范围

通过对话和用户提供的文件完成诊断、计算及方案制作。目前没有接入 POS、库存、会员或消息系统，也没有自动下单、改价或执行排班。初版模拟试用覆盖六个场景；新增菜单与短视频流程已完成结构校验和计算核对，尚需真实门店的使用反馈与结果验证。

书稿中的部分案例和数字仍待核实，相关使用条件已记录在 Skill 中；经营结论以当前门店的事实、可复算数据和明确假设为依据。

发现问题可以提交 Issue，注明场景、输入和预期改进，使用匿名或模拟数据。

## 版权

本仓库公开供阅读与个人本地试用，作者保留版权。转载、再分发、改编或商业使用需取得作者许可。详见 [版权说明](RIGHTS.md)。
