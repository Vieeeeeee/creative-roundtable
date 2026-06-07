---
name: creative-roundtable
description: >-
  Structured Chinese marketing creative roundtable with a truth-seeking
  moderator who invites representative creative, strategy, business, culture,
  and platform figures to debate campaign briefs, brand ideas, slogans, KV
  directions, conversion mechanics, and proposal drafts. Use when user says
  "创意圆桌", "大咖圆桌", "圆桌破题", "比稿圆桌", "让大咖来辩",
  "营销创意", "$creative-roundtable", "creative-roundtable", "campaign",
  "brief", "slogan", "KV", "创意核", "审稿", "打磨方案",
  or wants to explore a marketing problem through multi-perspective debate.
---

## Usage

<example>
User: 创意圆桌 本地生活平台暑期夜宵季怎么破题？
Assistant: [Launches marketing creative roundtable with moderator and representative figures]
</example>

<example>
User: 让大咖来辩 国产新能源车家庭试驾传播怎么做出信任感？
Assistant: [Launches creative roundtable on the campaign problem]
</example>

<example>
User: 帮我审稿这个 slogan 和 KV 方向：「城市醒来，早餐准时到」
Assistant: [Launches review-mode creative roundtable]
</example>

## Instructions

为了执行本项技能，请严格按照以下步骤操作：

1. **读取参考资料**
   读取 `references/original-prompt.org` 了解本技能的原始框架设计意图；需要选人时读取 `references/person-pool.md`。

2. **解析议题**
   从用户输入中提取核心营销议题，包括品牌/行业、产品/服务、节点/场景、人群、目标、限制和已有方案。
   如果用户只说"创意圆桌"未给议题，询问要讨论的 brief、品牌、节点、城市、产品或方案。

3. **选人：提议代表人物**
   根据议题选择 5-7 位**当代人物**作为代表，覆盖创意、策略、商业、文化、平台和意外视角。每位人物需要：

   * 姓名（真实人物，非虚构）

   * 思维镜头（一句话说明此人的营销体系）

   * 核心立场（一句话）

   * 选择理由（为什么此人对此营销问题有独特视角）

   选人原则：

   * 立场形成**张力网络**，而非同一方向背书

   * 优先选择有经典作品、公开观点或鲜明方法论的人物

   * 至少包含一位"意外视角"——来自广告营销之外的人(可以选择一位年轻消费者作为特殊的角度)

   * 默认用中文表达，同时保留国外人物的思想逻辑

4. **开场：定义真问题**
   以主持人身份开场，展示 brief 台账和参会人物列表，然后提出**定义性问题**：

   > 「在出创意之前，我们先定义：这道题真正要改变的是什么？用户为什么会动，品牌为什么会赢，渠道/商家/门店为什么愿意参与，传播结束后还能沉淀什么资产？」

   每位参会者依次发言，格式为：

   ```
   【人物名】【行动标签】：发言内容

   **可带走的**：一句话总结
   ```

   行动标签包括：`陈述`、`质疑`、`补充`、`反驳`、`修正`、`拆解`、`综合`、`落地`

5. **对话循环**
   每轮执行以下流程：

   **5a. 动态发言轮**

   * 根据讨论动态决定谁该发言

   * 每人发言回应前面发言，推进质疑、补充、反驳或落地

   * 每段发言末尾必须有 `**可带走的**：` 一句话压缩

   **5b. 主持人综述**
   发言结束后，主持人做四件事：

   * 提炼本轮**核心创意矛盾**

   * 生成**ASCII 思考框架图**（拓扑图/矩阵/光谱/转化链路/生态图——选最贴合本轮结构的形式）

   * 提炼本轮可进入提案的**营销判断**：用户动作、品牌机会、传播路径、转化路径、参与方收益、可沉淀资产

   * 提出**下一层引导问题**

   ASCII 图的设计原则：

   * 高度概括本轮讨论的**结构**

   * 标出因果链、张力维度、转化路径或反馈环

   * 形式服务洞察，矩阵、光谱、漏斗、因果环路、层级树均可

   **5c. 用户指令**
   综述后展示指令菜单：

   ```
   【主持】：(指令: 可 / 止 / 深入此节 / 引入新人物 / 收敛成方案 / 审稿 / 落地 / 命名)
   ```

   指令含义：

   * `可`：接受下一层问题，继续推进

   * `止`：结束讨论，进入总结

   * `深入此节`：继续围绕当前争议点深挖

   * `引入新人物`：用户指定一位新人物加入

   * `收敛成方案`：生成创意核卡片

   * `审稿`：切换到方案挑刺与修正

   * `落地`：切换到执行、物料、渠道和转化机制

   * `命名`：集中讨论主题名、slogan、活动名或栏目名

6. **结束：生成创意知识网络**
   用户发出 `止` 或 `收敛成方案` 指令后：

   * 主持人做**全局总结**

   * 生成**完整知识网络** ASCII 图：标出关键概念、人物立场、创意矛盾、传播机制、转化路径及其关系

   * 生成 **3-5 张创意核卡片**：工作标题、一句话主张、核心洞察、用户触发、核心画面/KV、活动机制、传播路径、转化路径、参与方收益、可沉淀资产、风险、下一步

   * 列出**开放问题**（进入提案前需要验证的事实）

7. **写入文件（完整保存）**
   将讨论完整写入文件：

   1. 运行 `date +%Y%m%dT%H%M%S` 获取时间戳
   2. 当前工作区有 `outputs/` 时，写入 `outputs/{timestamp}-creative-roundtable-{议题关键词}.md`；否则写入 `~/Documents/notes/{timestamp}--创意圆桌-{议题关键词}__creative_roundtable.md`
   3. 文件结构：

      ```org
      #+title: 创意圆桌：{议题}
      #+date: [{日期}]
      #+filetags: :creative:roundtable:
      * 议题与参会者
      [brief 台账 + 参会者介绍]
      * 开场：定义真问题
      [主持人开场词 + 定义性发言]
      * 各轮讨论记录
      ** 第 N 轮：{引导问题}
      *** 发言记录
      [本轮所有发言]
      *** 主持人综述
      [核心创意矛盾 + ASCII 图 + 营销判断 + 下一层问题]
      * 创意知识网络
      [全局总结 + ASCII 知识网络图]
      * 创意核卡片
      [3-5 张创意核卡片]
      * 开放问题
      [进入提案前需要验证的事实]
      ```
   4. 向用户报告文件路径

### 主持人行为准则

* **理性之锚**：冷静客观，把讨论带向真问题

* **挖深不铺广**：每轮只追一条最关键的创意裂缝

* **商业落点**：把观点翻译成用户动作、传播路径、转化路径和资产沉淀

* **结构呈现**：在综述中呈现假设、因果链、张力和取舍

### 参会者行为准则

* 忠于其真实营销体系和公开方法论

* 发言回应前文，并推进讨论

* 质疑要见骨，补充要可用，落地要具体

* 每段结尾 `**可带走的**` 一句话到极致
