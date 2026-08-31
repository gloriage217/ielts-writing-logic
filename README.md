# IELTS Writing Underlying Logic

[中文](#中文说明) · [English](#english)

An open-source, cross-platform Agent Skill for **Codex**, **Qwen Code**, **Claude Code**, **Gemini CLI**, and **Cursor**. It supports IELTS Writing Task 1 charts and Task 2 essays, helping learners analyse a prompt, build a defensible position, write annotated model essays, and diagnose drafts against Task Response, Coherence and Cohesion, Lexical Resource, and Grammatical Range and Accuracy.

## What it does

- Generates Task 2 model essays with question-type analysis, a stance path, SEESC paragraph annotations, and a correspondence check.
- Reviews learner essays using the TR / CC / LR / GR criteria and rewrites only the weakest paragraph.
- Runs a three-round Socratic practice mode for learners who want guided practice rather than an immediate answer.
- Supports Task 1 **chart** questions with an Overall + grouping + comparison approach.

## The underlying-logic method

This is not a bank of interchangeable phrases. The method begins **before** drafting: it turns an IELTS question into a decision about the relationship between its two ideas, then turns that decision into a paragraph-level proof.

```text
Question with A and B
        |
        +-- Can A and B work together?
        |       |
        |       +-- Yes → coexistence stance
        |       |          combine A with B / joint effort / work together
        |       |
        |       +-- Not at the same time → reconcile on a timeline
        |                  short term: A; long term: B
        |
        +-- Do A and B genuinely conflict, or does the question use an absolute claim?
                |
                +-- Yes → leaning stance
                           acknowledge A is meaningful
                           show the problem A cannot solve but B can
```

For example, *competition versus cooperation* is not automatically an “either/or” question: cooperation can govern team work while healthy competition builds personal drive, so the stance is that the two should be combined. But when a prompt claims that longer prison sentences are **the best** way to reduce crime, the method first makes the claim reasonable — prison is a meaningful deterrent — and then tests its ceiling: punishment cannot remove root causes such as lack of skills or legal awareness, whereas education can. This produces a precise position instead of an empty “both sides are right”.

### SEESC: the paragraph engine

After choosing a stance, each body paragraph follows **SEESC** — a five-step reasoning chain that prevents the common “claim + example” jump.

| Step | Meaning | Job in the paragraph |
| --- | --- | --- |
| **S** | **Standpoint** (论点) | State the point this paragraph will prove. |
| **E** | **Explanation** (因果剖析) | Explain why it happens; make the causal link visible. |
| **E** | **Example / evidence** (例证) | Give a concrete, relevant illustration rather than a loose story. |
| **S** | **Substitution reasoning** (置换推理) | Change a condition and reason forward or backward: *if / without / unless …, what follows?* |
| **C** | **Conclusion** (小结) | Close the chain and reconnect it to the stance. |

The second **S** is the signature move. Rather than adding another example, it tests the argument under a changed condition. For instance: *If governments improve literacy and job skills, fewer people will need to rely on crime for survival.* That conditional consequence shows why the earlier explanation actually supports the claim.

### What makes the method different

- **Stance is a reasoning choice, not a preference.** It distinguishes coexistence, real conflict, absolute claims, and time-based sequencing.
- **“A has value” is not “A is best.”** The method keeps the useful part of an opposing view, then compares what each option can and cannot solve.
- **A paragraph must travel somewhere.** SEESC adds causal explanation, a grounded illustration, and a conditional/counterfactual test — not just polished vocabulary.
- **Task 1 uses the same discipline.** First state the overall pattern, then group data by shared movement or contrast instead of reporting each year mechanically.

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

### 这套方法的底层逻辑

它不是句型库，而是一套“**先决策，再论证**”的写作系统。

1. 先判断题目中的 A / B 是**共存**还是**矛盾**。
   - 能互补：立场要明确写“结合才是答案”（`combine with` / `the joint effort` / `work together`），不是模糊地说“两边都对”。
   - 同一时刻冲突、但可分阶段：用时间轴破题（短期 A、长期 B；或先 A 后 B）。
   - 真正冲突或题干有 `the best`、`the only`、`the key` 等绝对表达：先承认 A **有意义**，再指出 A 解决不了、但 B 能解决的更高层问题。
2. 再用 **SEESC** 把立场变成可检验的论证链，而不是“观点后面堆一个例子”。

### SEESC 是什么？

| 字母 | 含义 | 这一句要完成的任务 |
| --- | --- | --- |
| **S** | 论点（Standpoint） | 这段到底要证明什么？ |
| **E** | 因果剖析（Explanation） | 为什么成立？把因果链说出来。 |
| **E** | 例证（Example / evidence） | 用具体的人、事、场景或可信证据落地。 |
| **S** | 置换推理（Substitution reasoning） | 换个条件再推一遍：`if / without / unless` 之后会怎样？ |
| **C** | 小结（Conclusion） | 收束并回扣本段与全文立场。 |

其中第二个 **S（置换推理）** 是招牌步骤：不是再加一个例子，而是让论证经得起“如果这样 / 如果不这样”的检验。例如，教育能预防犯罪，不只因为它有价值；还因为**如果**政府改善识字率和职业技能，更多人便能合法谋生，犯罪诱因会相应减少。

这让你的作文从“我觉得 A 好”走到“在什么条件下，为什么 A 能产生什么结果”。

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
