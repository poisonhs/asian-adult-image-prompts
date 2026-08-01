# Asian Adult Image Prompts

为 Codex 提供成年、虚构、亚洲风格 editorial 或 boudoir 图像提示词的技能。它会组合场景、构图、服装、光线、姿势与表情，生成连贯的英文图像提示词。

## 安装

需要已安装 Codex 和 Git。个人技能默认目录是 `~/.agents/skills`。

首次安装：

```bash
git clone https://github.com/poisonhs/asian-adult-image-prompts.git \
  ~/.agents/skills/asian-adult-image-prompts
```

重新打开 Codex 会话后，技能会自动发现。

如果该目录已经是本仓库的 Git 工作副本，更新即可：

```bash
git -C ~/.agents/skills/asian-adult-image-prompts pull --ff-only
```

如果目录已存在但没有 `.git`，不要直接覆盖。先备份或移走旧目录，再执行首次安装命令，以保留后续的提交和更新能力。

## 使用

在 Codex 对话中显式调用技能，并说明画面需求：

```text
使用 $asian-adult-image-prompts：
创作一张成年、虚构的亚洲女性时尚私房摄影提示词。
室内自然侧光，半身构图，深色丝绸睡袍，克制优雅。
输出英文 Prompt 和 Negative prompt。
```

也可以使用简短形式：

```text
$asian-adult-image-prompts
成年虚构人物，日系杂志风私房摄影，柔光，85mm 镜头。
```

未指定输出格式时，技能返回中文 Brief、英文 Prompt 和可选 Negative prompt。提示词默认控制在 80 至 180 个英文词之间。

## 边界

- 仅限明确成年、虚构且自愿的主体。
- 不生成涉及胁迫、乱伦、剥削、动物或真人色情化的内容。
- 年龄、同意或人物身份不明确时，技能会要求澄清。
- 本仓库中的参考映射用于辅助生成，不应整段复制或重新分发其来源内容。

## 仓库内容

- `SKILL.md`：技能的运行时指引。
- `agents/openai.yaml`：Codex 界面元数据。
- `references/source-map.md`：本地参考源、版本和归属要求。

## 开发与校验

修改技能后运行：

```bash
python3 /root/.codex/skills/.system/skill-creator/scripts/quick_validate.py .
```

该命令需要本机已安装 Codex 的 Skill Creator。发布前确认 `SKILL.md`、`agents/openai.yaml` 和 `references/source-map.md` 都在提交中。
