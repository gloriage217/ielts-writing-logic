# IELTS Writing Underlying Logic

[中文](#中文说明) · [English](#english)

An open-source, cross-platform Agent Skill for **Codex**, **Qwen Code**, **Claude Code**, **Gemini CLI**, and **Cursor**. It supports IELTS Writing Task 1 charts and Task 2 essays, helping learners analyse a prompt, build a defensible position, write annotated model essays, and diagnose drafts against Task Response, Coherence and Cohesion, Lexical Resource, and Grammatical Range and Accuracy.

## What it does

- Generates Task 2 model essays with question-type analysis, a stance path, SEESC paragraph annotations, and a correspondence check.
- Reviews learner essays using the TR / CC / LR / GR criteria and rewrites only the weakest paragraph.
- Runs a three-round Socratic practice mode for learners who want guided practice rather than an immediate answer.
- Supports Task 1 **chart** questions with an Overall + grouping + comparison approach.

## Installation

Clone or download this repository, then install it for your preferred agent.

### Codex

Copy the folder into your local Codex skills directory:

```bash
git clone https://github.com/gloriage217/ielts-writing-logic.git
mkdir -p ~/.codex/skills
cp -R ielts-writing-logic ~/.codex/skills/ielts-writing-logic
```

Start a new Codex conversation after installation. You can also package the skill as an archive:

```bash
cd ielts-writing-logic
zip -r ielts-writing-logic.skill SKILL.md .skill-metadata.yaml references
```

### Qwen Code

Copy the same folder into Qwen Code's personal skills directory:

```bash
git clone https://github.com/gloriage217/ielts-writing-logic.git
mkdir -p ~/.qwen/skills
cp -R ielts-writing-logic ~/.qwen/skills/ielts-writing-logic
```

Run `qwen` from a terminal, then invoke the skill with `/ielts-writing-logic`, or simply ask an IELTS Writing question and let Qwen Code select it automatically.

### Claude Code

Copy the folder into Claude Code's personal skills directory:

```bash
git clone https://github.com/gloriage217/ielts-writing-logic.git
mkdir -p ~/.claude/skills
cp -R ielts-writing-logic ~/.claude/skills/ielts-writing-logic
```

Start Claude Code and type `/ielts-writing-logic`, or ask an IELTS Writing question for automatic activation.

### Gemini CLI

Gemini CLI can install the repository directly:

```bash
gemini skills install https://github.com/gloriage217/ielts-writing-logic
```

Use `/skills list` to verify discovery. Gemini CLI asks for approval when a skill is activated.

### Cursor

Copy the folder into Cursor's personal skills directory:

```bash
git clone https://github.com/gloriage217/ielts-writing-logic.git
mkdir -p ~/.cursor/skills
cp -R ielts-writing-logic ~/.cursor/skills/ielts-writing-logic
```

Use `/ielts-writing-logic` in Cursor Agent, or let Cursor select it when the request matches.

### Shared installation for Gemini CLI and Cursor

Both platforms also discover skills under `~/.agents/skills/`. Install the folder there once if the same computer uses both agents:

```bash
mkdir -p ~/.agents/skills
cp -R ielts-writing-logic ~/.agents/skills/ielts-writing-logic
```

## Usage

In Codex, use the skill explicitly with `$ielts-writing-logic`, or provide a matching IELTS Writing task and let Codex select it automatically. In Qwen Code, invoke it with `/ielts-writing-logic`.

```text
$ielts-writing-logic
Please review my IELTS Task 2 essay.

Question: Some people think ... To what extent do you agree or disagree?
Essay: [paste your essay]
```

```text
$ielts-writing-logic
Teach me this question step by step. Do not give me a model essay first.

Question: [paste an IELTS Writing question]
```

## Scope

- Method explanations are in Chinese; model essays, sentence patterns, and examples are in English.
- The default target is approximately Band 6.5–7 performance. This skill does not guarantee an IELTS score.
- Task 1 maps and process diagrams are outside the current scope.
- This project is intended for IELTS Writing only, not TOEFL, CET, or postgraduate entrance-exam writing.

## Repository structure

```text
.
├── SKILL.md                 # Main workflow and routing rules
├── .skill-metadata.yaml     # Optional invocation metadata
└── references/
    ├── method.md            # Decision trees, frameworks, and language upgrades
    ├── sentence-bank.md     # Reusable sentence patterns
    ├── example-bank.md      # Example and idea bank
    └── sample-essays.md     # Annotated benchmark essays
```

## Contributing

Contributions are welcome. Please keep additions specific to IELTS Writing, avoid unverifiable statistics, and ensure sample materials are original or licensed for redistribution. Do not submit students' personal essays without their explicit permission.

## License

This project is licensed under the [MIT License](LICENSE).

---

## 中文说明

这是一个跨平台代理的雅思写作技能，支持 Codex、Qwen Code、Claude Code、Gemini CLI 和 Cursor：可判定题型和立场、生成带 SEESC 标注的范文、按 TR／CC／LR／GR 批改作文，并以苏格拉底式方式带练。

### 怎么用

安装后，在新对话中直接发雅思题目或作文即可。Codex 可显式输入：

```text
$ielts-writing-logic 批改我的作文。
原题：……
作文：……
```

Qwen Code 中则输入：

```text
/ielts-writing-logic
```

Claude Code、Gemini CLI 和 Cursor 也可以使用 `/ielts-writing-logic`。普通聊天网页版（例如通义千问聊天网页）若没有 Skills 功能，不能直接安装本地 Skill。

只给题目时会生成范文；给出作文时会批改；说“教我”“带我练”或“先别给答案”时会进入互动练习模式。

### 开源注意事项

- 请勿上传学生姓名、联系方式、未获授权的学生作文或付费课程原文。
- 范文和事例应避免编造具体统计数据。
- 本项目用于学习辅助，不构成对任何考试分数的承诺。
