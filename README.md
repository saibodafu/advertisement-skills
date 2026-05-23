# advertisement-skills — Claude Code / Codex 广告技能包

> 把广告策略、创意简报、媒介规划、投放复盘等广告工作流沉淀成可复用的 Agent skills。

---

## 安装

### Claude Code 快速安装

在 Claude Code 中添加这个 GitHub 仓库作为插件市场来源：

```text
/plugin marketplace add saibodafu/advertisement-skills
```

然后安装插件：

```text
/plugin install advertisement-skills
```

重启 Claude Code 后，用 `/skills` 检查是否已加载广告技能。

### Claude Code 手动安装

```bash
git clone https://github.com/saibodafu/advertisement-skills.git
cc --plugin-dir ./advertisement-skills
```

也可以使用 SSH：

```bash
git clone git@github.com:saibodafu/advertisement-skills.git
cc --plugin-dir ./advertisement-skills
```

### Codex 使用

在 Codex 中打开本仓库目录即可使用：

```bash
git clone https://github.com/saibodafu/advertisement-skills.git
cd advertisement-skills
```

Codex 会读取 `AGENTS.md`、`.codex-plugin/plugin.json`、`commands/` 和 `skills/` 中的说明。你可以直接说：

```text
使用 advertisement-skills 的 ad-brief，帮我把这个投放需求整理成广告创意简报。
```

或者：

```text
使用 media-plan，帮我为这个产品做一版广告媒介规划。
```

也可以使用：

```text
使用 creative-review，帮我审一下这组广告创意，指出风险和优化方向。
```

或者：

```text
使用 seedance-short-drama-storyboard，把这个短剧剧本按 15 秒拆成 Seedance 2.0 分镜提示词。
```

---

## 使用方式

### Claude Code 命令

```text
/advertisement ad-brief 为一个广告投放需求生成创意简报
/advertisement media-plan 为一个产品或活动规划广告媒介组合
/advertisement creative-review 审核广告创意并给出优化建议
/advertisement seedance-short-drama-storyboard 把短剧剧本拆成 Seedance 2.0 的 15 秒分镜 Block
```

以下自然语言也适合触发：

- “帮我写一份广告 brief”
- “把这个投放需求整理成广告创意简报”
- “帮我规划这波广告投放渠道”
- “审一下这组广告创意”
- “帮我判断这个广告素材哪里可以优化”
- “把这个短剧剧本拆成 Seedance 分镜提示词”
- “按 15 秒一个 Block 拆分这个剧情”

---

## 当前 Skills

### ad-brief

把粗略的投放需求整理成一份广告创意简报，适合品牌广告、效果广告、达人投放、信息流素材、短视频广告和落地页前置规划。

输出重点：

- 广告目标
- 目标人群
- 核心洞察
- 传播主张
- 创意方向
- 素材规格
- CTA 和衡量指标

### media-plan

根据广告目标、预算、周期、人群和产品特征，规划媒介组合、渠道分工、投放节奏和基础衡量方式。

输出重点：

- 投放目标
- 渠道组合
- 预算分配逻辑
- 阶段节奏
- 素材需求
- 数据指标

### creative-review

从策略、创意、表达、合规和转化路径角度审核广告创意，输出问题清单和可执行优化建议。

输出重点：

- 核心问题
- 风险判断
- 优化优先级
- 文案和画面修改方向
- 下一版测试建议

### seedance-short-drama-storyboard

把完整短剧剧情、广告短剧脚本或口播剧情拆成 Seedance 2.0 可用的连续 15 秒分镜 Block。

输出重点：

- 15 秒连续 Block
- BGM 起承转合
- Seedance 友好运镜
- 画面微细节
- 简短有力对白
- 动作衔接转场

---

## GitHub 仓库

- HTTPS：[https://github.com/saibodafu/advertisement-skills](https://github.com/saibodafu/advertisement-skills)
- SSH：`git@github.com:saibodafu/advertisement-skills.git`

---

## 项目结构

```text
.
├── .claude-plugin/
│   ├── marketplace.json
│   └── plugin.json
├── .codex-plugin/
│   └── plugin.json
├── commands/
│   └── advertisement.md
└── skills/
    ├── ad-brief/
    │   └── SKILL.md
    ├── creative-review/
    │   └── SKILL.md
    ├── media-plan/
    │   └── SKILL.md
    └── seedance-short-drama-storyboard/
        └── SKILL.md
```

---

## 新增 Skill

1. 创建 `skills/<skill-name>/SKILL.md`。
2. 如果 workflow 需要复用脚本，把脚本放在 `skills/<skill-name>/scripts/`。
3. 如果需要命令入口，在 `commands/` 下新增 markdown 命令文件。
4. 如果市场定位、关键词或产品描述变化，同步更新 `.claude-plugin/marketplace.json` 和 `.codex-plugin/plugin.json`。

新增 skill 时，应先澄清场景、目标用户、输入、输出、边界、触发条件和质量标准；确认方向后再写入 skill 文件。

---

## 说明

- `.claude-plugin` 用于 Claude Code 插件和 marketplace 风格描述。
- `.codex-plugin` 用于 Codex 插件清单兼容。
- `commands/advertisement.md` 提供 `/advertisement` 命令入口。
- `skills/` 是每个广告 workflow 的主说明。
- 输出应能直接交给策略、创意、媒介、投放、设计或销售团队使用，不编造市场数据、平台规则、预算效果或客户案例。
