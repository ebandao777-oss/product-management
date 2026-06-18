---
name: product-management
description:
  产品管理技能套件：PRD生成、产品脑暴、指标复盘、用户反馈分析、用户故事拆解、竞品分析、路线图更新、需求优先级排序。
  PRD生成: PRD生成, 写PRD, 需求文档, 功能规格; 产品脑暴: 产品脑暴, 头脑风暴, brainstorm, 创意发散; 指标复盘: 指标复盘, 数据复盘, DAU分析, 转化漏斗; 用户反馈分析: 用户反馈分析, 用户反馈, 用户声音, NPS分析; 用户故事拆解: 用户故事拆解, 用户故事, story拆分, 敏捷需求; 竞品分析: 竞品分析, 竞品调研, 竞品跟踪, 功能对比; 路线图更新: 路线图更新, roadmap, 版本规划, 排期; 需求排序: 需求排序, 需求优先级, RICE, Kano模型。
version: "1.0.1"
author: "智慧半岛"
---

# product-management -- 产品管理综合技能

本技能是一个综合技能套件，包含多个子技能。接到用户请求后，按以下流程执行。

## 执行流程

### Step 1: 意图识别与路由匹配

分析用户输入，与下方路由表逐一比对。匹配规则：
- 用户输入中包含路由表中「子技能」列的关键词 → 匹配该子技能
- 用户输入中包含路由表中「功能说明」列中提到的场景 → 匹配该子技能
- 多个子技能同时匹配时，选择匹配度最高的
- 无法唯一确定时，向用户确认意图

### Step 2: 加载子技能模板

匹配到子技能后，根据子技能索引表找到对应的文件路径，**必须**使用 `read_text` 工具读取 `references/` 目录下的完整执行模板。

### Step 3: 按模板执行

严格按照加载的模板逐步执行。模板中定义了：
- 输入要求（用户需要提供什么）
- 执行步骤（每一步做什么、如何判断）
- 输出格式（最终产出的结构和规范）
- 质量标准（产出必须满足的底线）

### Step 4: 输出结果

按模板规定的格式输出结果。如果模板要求生成文件，写入后声明产出物。

## 约束规则

1. **必须先读模板再执行**：匹配到子技能后，严禁凭记忆或猜测执行，必须先读取对应的 references 文件
2. **严格遵循模板**：不得跳过步骤、不得省略检查项、不得自行简化流程
3. **输入不足时主动索取**：模板中标注「必填」的输入项缺失时，向用户索取
4. **质量底线不妥协**：模板中的质量标准必须逐条满足

## 路由表

| 子技能 | 功能说明 |
|--------|----------|
| PRD生成 | 输入功能需求描述，生成结构化PRD文档，含背景分析、目标定义、功能清单、交互... |
| 产品指标复盘 | 输入产品指标数据或时间周期，输出指标健康度评估、趋势分析、归因分析和行动建议。 |
| 产品脑暴 | 围绕产品问题或机会点进行结构化创意发散，输出经过初步筛选的创意清单。 |
| 用户反馈分析 | 上传用户反馈数据（Excel/CSV/文本），自动分类统计并提取高频模式... |
| 用户故事拆解 | 从Epic或大需求中拆解出独立可交付的User Story... |
| 竞品分析 | 输入竞品列表或产品方向，输出功能对比矩阵、SWOT分析、Porter五力分析... |
| 路线图更新 | 汇总迭代状态、评估里程碑进度、记录优先级变更... |
| 需求优先级排序 | 输入需求列表，用RICE/ICE/MoSCoW/Kano模型辅助排序... |

## 子技能索引

| 子技能 | 英文标识 | 文件 |
|--------|----------|------|
| PRD生成 | `prd-generation` | [references/prd-generation.md](./references/prd-generation.md) |
| 产品指标复盘 | `product-metrics-review` | [references/product-metrics-review.md](./references/product-metrics-review.md) |
| 产品脑暴 | `product-brainstorm` | [references/product-brainstorm.md](./references/product-brainstorm.md) |
| 用户反馈分析 | `user-feedback-analysis` | [references/user-feedback-analysis.md](./references/user-feedback-analysis.md) |
| 用户故事拆解 | `user-story-breakdown` | [references/user-story-breakdown.md](./references/user-story-breakdown.md) |
| 竞品分析 | `competitive-analysis` | [references/competitive-analysis.md](./references/competitive-analysis.md) |
| 路线图更新 | `roadmap-update` | [references/roadmap-update.md](./references/roadmap-update.md) |
| 需求优先级排序 | `requirement-prioritization` | [references/requirement-prioritization.md](./references/requirement-prioritization.md) |
## 跨技能协同指引

| 协同技能 | 典型场景 |
|---------|---------|
| 市场营销 | PRD通过后调用市场营销生成配套营销文案 |

> 以上为推荐协同路径。执行复合任务时，请根据实际需求灵活组合。

## 变更日志

### v1.0.1 (2026-06-19)
- 对齐 description 子技能名与路由表名称
- 压缩路由表说明列至40字以内
- 新增跨技能协同指引章节
- 删除冗余英文 description 行