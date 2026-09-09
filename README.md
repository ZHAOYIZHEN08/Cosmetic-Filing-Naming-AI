# Cosmetic Naming AI

一个用于**中国大陆化妆品产品命名**的 AI Skill 原型。

它不是简单地“让 AI 想几个名字”。它会先读取产品类目、剂型、功效、命名重点和风格，再从不同命名方向生成候选，并对明显的法规风险、功效暗示和产品事实进行预筛。

这个项目目前由两部分组成：

- **Naming Brief Builder**：一个可以直接点击和选择的网页，用来整理产品信息。
- **SKILL.md**：告诉 AI 应该怎样理解 Brief、生成名字、筛选风险和处理后续修改。

Brief Builder 是纯静态网页，**不调用 OpenAI API，不需要 API Key，也不会因为填写表单产生额外 API token 费用。**

---

## 它适合做什么？

你可以用它来：

- 给护肤、彩妆、头发与头皮、身体个护、香氛产品做中文命名；
- 把类目、剂型、使用方法、功效等信息先标准化；
- 设置希望的命名风格，例如更功效、更高级、更年轻、更克制；
- 设置不希望出现的感觉，例如药感、少女感、古风；
- 让 AI 从不同 Naming Strategy 生成候选；
- 对生造词、拗口表达和明显的法规语义风险做一轮预筛；
- 为创意词生成简短的 Naming explanation / Filing basis。

---

## 最简单的使用方法

### 第一步：打开 Naming Brief Builder

点击下面的链接进入交互式产品信息面板：

### 👉 [打开 Naming Brief Builder](https://zhaoyizhen08.github.io/Cosmetic-Filing-Naming-AI/intake/)

无需登录，无需 API Key。填写产品类目、剂型、功效和命名风格后，可以直接生成标准化 Naming Brief。

---

### 第二步：填写产品信息

在网页里选择：

- 产品类目
- 剂型
- 使用方法
- 使用部位
- 备案地区
- 备案功效
- Naming Priority
- 命名风格
- Avoid

成分、技术、肤感、系列资产等信息没有的话可以不填。

---

### 第三步：生成并复制 Naming Brief

填完后点击：

**生成 Naming Brief → 复制完整 Prompt**

网页会把你的选择整理成一份 AI 可以直接读取的结构化 Brief。

---

### 第四步：在 ChatGPT 中使用 Skill

新建一个 ChatGPT 对话。

建议只上传：

`SKILL.md`

然后把刚才复制的 Naming Brief 粘贴进对话。

你可以先说：

> 请读取上传的 SKILL.md 作为本次化妆品命名工作流。下面的 Naming Brief 已经通过 Builder 标准化，请直接按 Skill 执行。

然后粘贴 Brief。

AI 会直接读取已经确认的信息，不应该重新让你填写一遍。

---

## 后续怎么修改？

看到第一轮候选后，可以直接说：

- “4号不错，但再顺口一点。”
- “整体更有创意，但不要降低法规标准。”
- “沿2号方向再来6个。”
- “不要这么多AI生造词。”
- “展开1、3、5的法规和备案解释。”

v0.3 的设计原则是：**只修改你明确提出的部分。**

例如“再顺口一点”应该提高语言自然度，而不是自动把所有名字变成最保守的功效直述。

所有新生成的名字，包括追问中的候选，都应该重新经过法规语义和事实检查后再展示。

---

## 为什么要用 Brief Builder？

如果完全靠聊天输入，用户可能会写：

> 一个洗掉的修护面膜

也可能写：

> rinse-off cream mask

还可能直接写法规术语。

Builder 的作用就是把不同输入统一成标准字段，再交给 AI。

简单来说：

**Builder 负责把信息整理清楚，Skill 负责思考和命名。**

---

## 当前限制

这个项目目前是一个原型，需要注意：

- 法规判断只是预筛，不代表正式备案一定通过；
- 不会自动完成商标注册检索；
- Trademark 默认是 `Not checked`；
- 如果没有实时市场数据，Market Collision 只能做有限判断；
- 法规信息需要持续更新；
- 最终产品名称仍建议由品牌、产品和法规人员共同确认。

---

## 文件结构

```text
cosmetic-naming-ai/
├── SKILL.md
├── README.md
├── NOTICE.md
├── index.html
├── intake/
│   └── index.html
└── docs/
    └── GITHUB_UPLOAD_CN.md
```

---

## 版本

Current runtime skill: **v0.3**

主要改进：

- 减少 AI 生造词和拗口组合；
- 新增 Linguistic Naturalness Gate；
- “更顺口”不再自动等于“更保守”；
- 每一轮新候选都必须重新经过 Universal Display Gate；
- 增加对“清醒 / 提神 / 助眠 / 排毒”等非化妆品语义的反查；
- 所有轮次保持统一的 Compact Candidate Card 输出。
