# IELTS Writing Underlying Logic

[中文](#中文说明) · [English](#english)

An open-source, cross-platform Agent Skill for **Codex**, **Qwen Code**, **Claude Code**, **Gemini CLI**, and **Cursor**. It supports IELTS Writing Task 1 charts and Task 2 essays, helping learners analyse a prompt, build a defensible position, write annotated model essays, and diagnose drafts against Task Response, Coherence and Cohesion, Lexical Resource, and Grammatical Range and Accuracy.

## What it does

- Generates Task 2 model essays with question-type analysis, a stance path, SEESC paragraph annotations, and a correspondence check.
- Reviews learner essays using the TR / CC / LR / GR criteria and rewrites only the weakest paragraph.
- Runs a three-round Socratic practice mode for learners who want guided practice rather than an immediate answer.
- Supports Task 1 **chart** questions with an Overall + grouping + comparison approach.

## The underlying-logic method

This is not a bank of interchangeable phrases. It is a **type-first writing system**: identify what the question asks, choose that question type's logic, then build each paragraph as proof. The same A/B decision must not be forced onto every Task 2 prompt.

```text
Task 2 prompt
    |
    +-- Agree / disagree → evaluate the claim and state a clear degree of agreement
    +-- Discuss both views → analyse the A/B relationship before choosing a position
    +-- Positive / negative development → weigh benefits against drawbacks
    +-- Causes / problems + solutions → diagnose causes, then match each cause to a remedy
```

### Four Task 2 routes

| Question type | First decision | Writing logic |
| --- | --- | --- |
| **Agree / disagree** | How far does the claim hold? | Take a clear, defensible degree of agreement; build non-overlapping reasons, with a limited concession where useful. |
| **Discuss both views** | What is the relationship between A and B? | Use the A/B decision route below; represent both views and state your own position. |
| **Positive / negative development** | Which side carries more weight? | Give the dominant side a full argument, acknowledge the cost, then land on a comparative judgement: benefits **far outweigh** limitations (or the reverse). |
| **Causes / problems + solutions** | What produces the problem, and what can address it? | Diagnose first, prescribe second. Each recommendation must treat a named cause rather than merely sound attractive. |

### The A/B route — for *Discuss both views* only

For a discussion prompt, *competition versus cooperation* is not automatically an “either/or” question: cooperation can govern team work while healthy competition builds personal drive, so the stance is that the two should be combined. If the options cannot operate at the same moment but make sense at different stages, reconcile them on a timeline — short term versus long term.

When the two views genuinely compete, especially where the prompt includes an absolute claim such as **the best**, first recognise the useful value of A, then test its ceiling: what problem can A not solve that B can? This produces a precise position instead of an empty “both sides are right”.

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

- **Question type determines the route.** It does not use one stance formula for four different prompts.
- **A/B analysis has a strict home.** Coexistence, conflict, absolute claims, and time-based sequencing belong to *Discuss both views* questions.
- **“A has value” is not “A is best.”** In a discussion question, the method keeps the useful part of an opposing view, then compares what each option can and cannot solve.
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

它不是句型库，而是一套“**先判题，再走对应路径，最后论证**”的写作系统。不同题型不能共用一把 A/B 的尺子。

| 题型 | 第一件事 | 专属解法 |
| --- | --- | --- |
| **同意与否** | 判断题干观点成立到什么程度 | 明确同意程度；用两条不撞车的理由证明，必要时做有限让步。 |
| **双边讨论** | 判断 A / B 的关系 | 才进入“共存 / 矛盾 / 拆时间 / 高低之分”的 A/B 决策。双方都要写，并给出自己的 opinion。 |
| **正负发展** | 判断利与弊谁的分量更重 | 优势（或劣势）完整展开，另一面让步，再用 `far outweigh` 落到权衡结论。 |
| **分析解决** | 找到原因／问题与对策的对应关系 | 先诊断，后开药；每一条建议要能治前面写出的具体原因。 |

**A/B 只服务于双边讨论题。**

- 能互补：立场要明确写“结合才是答案”（`combine with` / `the joint effort` / `work together`），不是模糊地说“两边都对”。
- 同一时刻冲突、但可分阶段：用时间轴破题（短期 A、长期 B；或先 A 后 B）。
- 真正冲突，或一方包含 `the best`、`the only`、`the key` 等绝对表达：先承认 A **有意义**，再指出 A 解决不了、但 B 能解决的更高层问题。

所有 Task 2 主体段再共同使用 **SEESC**：把立场变成可检验的论证链，而不是“观点后面堆一个例子”。

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

批改默认是**逐段精改**：先按 TR／CC／LR／GR 总诊断，再逐段说明问题、给出修改理由与修改版，最后提供全文整合版。修改段会逐句标出它在论证中的作用，如 `[S 论点]`、`[E 因果]`、`[E 例证]`、`[S2 置换推理]`、`[C 回扣]`；正负题还会标出“让步 / 权衡”。若只想快速获得方向，可以说“简改”或“只改最弱段”。

### 开源注意事项

- 请勿上传学生姓名、联系方式、未获授权的学生作文或付费课程原文。
- 范文和事例应避免编造具体统计数据。
- 本项目用于学习辅助，不构成对任何考试分数的承诺。
