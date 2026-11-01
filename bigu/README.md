# bigu · 辟谷食养

> 面向 Agent Skills 开放标准的辟谷知识技能。
> 建立：2026-10-24 ｜ 更新：2026-11-01

## 这是什么

一个符合 Agent Skills 开放标准的辟谷知识技能（Skill）。目标是让任何支持该标准的智能体（Claude Code、Codex、Cursor、Copilot、WorkBuddy 等）在用户问到辟谷时，能给出**有来源、有置信度、带安全边界**的回答，而不是泛泛的养生鸡汤。

## 结构

```
bigu/
├── SKILL.md                        # 入口：元数据 + 指令 + 五大能力细则
├── references/
│   ├── knowledge-atoms.jsonl       # 结构化知识原子（机器可读，一行一条，共 26 条）
│   ├── knowledge-atoms.md          # 人类可读版（001–010 亲测，011–026 公开文献整理改写）
│   ├── 复食阶梯.md                  # 复食两周阶梯、禁忌与活动建议
│   ├── 证据与出处.md                # 证据分层、交叉印证、文献冲突与延伸书目
│   └── safety.md                   # 安全红线与免责（最高优先级）
├── 大众版手册.md                    # 面向普通受众的精简手册（双形态之一）
└── README.md
```

## 署名

**作者 / 维护者：`leiboss`**（对外统一品牌名，非真名）。

## 知识原子字段

| 字段 | 含义 |
|---|---|
| `id` | 唯一编号（bigu-001 …） |
| `knowledge` | 提炼后的结论（一句话） |
| `original` | 原始记录片段或来源要点（已脱敏改写） |
| `source` | 来源：亲测实录 / 公开文献整理改写（非原文转载） |
| `date` | 日期 |
| `topics` | 主题标签 |
| `skills` | 关联能力（五大能力分类：knowledge/fit/plan/refeed/safety） |
| `type` | principle / method / case / anti-pattern / insight |
| `confidence` | high / medium / low |

## 双形态

| 形态 | 文件 | 适用 |
|---|---|---|
| 技能包 | `SKILL.md` + `references/` | 支持 Agent Skills 标准的智能体 |
| 大众版手册 | `大众版手册.md` | 不装技能、只看文档的普通受众 |

## 安装（验证用）

把整个 `bigu/` 目录复制到目标工具的 skills 目录：

- WorkBuddy：`~/.workbuddy/skills/bigu/`
- Claude Code：`~/.claude/skills/bigu/`
- 通用约定：`~/.agents/skills/bigu/`

> WorkBuddy 若通过其技能管理接口维护本地副本，需在 frontmatter 补 `agent_created: true`；开源标准版不带该私有字段。

## 合规边界（重要）

- **不含品牌名、产品名、价格、购买引导、分销话术**。
- **不含具体个人体重/体脂/身份数据**（已脱敏）。
- **不宣称疗效**，不出现「治疗/降糖/排毒/减肥神效/不反弹」等表述。
- 所有健康内容均带「非医疗建议」声明，并明确「不鼓励他人模仿」。
- 引用公开文献时只做**要点改写**，不转载原文；书目见 `references/证据与出处.md`。

## 许可证

**MIT**。选它的理由是最大化传播与二次使用。已知代价：他人可商用、可改后闭源。

若后续更在意「防止别人拿内容卖课」，可改 **CC BY-NC-SA 4.0**，代价是传播与商用场景受限。
