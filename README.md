# Second-Order Thinking | 二阶思维

A cognitive base that extends causal reasoning beyond first-order consequences. Works with any LLM agent — Claude, GPT, Gemini, or custom frameworks.

让 AI agent 的因果推理超越一阶后果，追踪连锁反应至 2-3 步。适用于任何 LLM agent — Claude、GPT、Gemini 或自定义框架。

---

## What it does | 它做什么

Most AI agents answer "what happens next?" and stop. Second-Order Thinking adds a reasoning layer that traces consequences 2-3 steps forward, tests counterfactuals ("what if we don't?"), and detects nonlinear tipping points where small forces produce outsized effects.

大多数 AI agent 回答"接下来会发生什么"就停了。二阶思维增加了一个推理层——追踪后果 2-3 步、测试反事实（"如果不做呢？"）、检测小力量在适当条件下产生非线性放大的临界点。

### Before (default agent) | 安装前

> "Should we add this feature?"
>
> "Yes, it addresses the top user request, aligns with your roadmap, and can be built in 2 sprints. Here's the implementation plan..."

### After (with Second-Order Thinking) | 安装后

> "The feature solves the immediate request, but: (1) it adds a permanent maintenance surface — every future feature must now account for it, compounding engineering cost by ~15% per quarter; (2) it signals to users that you respond to volume, training them to escalate requests rather than adapt workflows; (3) if you don't build it, 60% of requesters will find the existing workaround within 2 weeks — the counterfactual cost is lower than it appears. The real question is whether the 2nd-order maintenance burden justifies the 1st-order user satisfaction gain."

---

## How it works | 工作原理

**One core cognitive shift** applied to every reasoning task:

一个核心认知转换，应用于每一个推理任务：

| Default mode | Target mode |
|---|---|
| "What happens next?" then stop 问完"然后呢"就停 | "And then what? And then what?" — trace 2-3 steps 追问两三步 |
| Analyze only "what if we do it" 只分析"做了会怎样" | Also analyze "what if we don't" — counterfactual as control group 同时分析"不做会怎样"——反事实作为对照组 |
| Assume current trends continue 假设趋势延续 | Detect phase transitions — where does linear become nonlinear? 检测相变——线性何时变为非线性？ |

**Three absorbed frameworks**:

三个吸收的框架：

| Framework | Core insight | How it's used |
|---|---|---|
| Bastiat / Howard Marks: "Then what?" | Every action has consequences beyond the immediate; trace the chain 每个行动的后果超越当下 | The main reasoning loop — keep asking "and then what?" for 2-3 iterations |
| Counterfactual thinking (Kahneman / Roese) | "What if we didn't do this?" reverses the causal chain as a control group 反事实作为对照组 | Before committing, always run the null scenario |
| Mao's 星星之火 (A single spark can start a prairie fire) | Small forces under right conditions produce nonlinear amplification; tipping points 星星之火可以燎原 | Detect where consequences jump from linear to exponential |

**Five anti-patterns** that catch fake second-order thinking:

五个反模式，捕捉伪二阶思维：

| Anti-pattern 反模式 | Description 描述 |
|---|---|
| One-step stop 一步即停 | Concluding after immediate consequences without tracing further 分析完直接后果就停 |
| Infinite regression 无限回溯 | Tracing so far forward it becomes useless speculation 推演太远变成无用推测 |
| Parallel listing 平行罗列 | Listing N possible consequences without judging probability 罗列可能性不判断概率 |
| Ignoring counterfactual 忽略反事实 | Only analyzing "do it" without analyzing "don't do it" 只分析做不分析不做 |
| Linear extrapolation 线性外推 | Assuming trends continue without considering phase transitions 假设趋势延续忽略相变 |

---

## Installation | 安装

### Claude Code
```bash
cp cognitive-protocol.md ~/.claude/second-order-thinking.md
echo '@~/.claude/second-order-thinking.md' >> ~/.claude/CLAUDE.md
```

### Codex
```bash
cat cognitive-protocol.md >> AGENTS.md
```

### Gemini
Paste `cognitive-protocol.md` into `system_instruction`.

将 `cognitive-protocol.md` 内容粘贴到 `system_instruction` 中。

### Cursor
```bash
cat cognitive-protocol.md >> .cursorrules
```

### Any agent | 任何 agent
Inject `cognitive-protocol.md` (~30 lines) into the system prompt. See [`install/generic.md`](install/generic.md) for details.

将 `cognitive-protocol.md`（约 30 行）注入系统提示词。详见 [`install/generic.md`](install/generic.md)。

---

## File structure | 文件结构

```
second-order-thinking/
├── README.md                  ← You are here / 你在这里
├── cognitive-protocol.md      ← Core rules (~30 lines, always-on) / 核心规则（约 30 行，始终激活）
├── SKILL.md                   ← Full framework reference / 完整框架参考
├── anti-patterns.md           ← Detailed anti-pattern guide / 反模式详解
├── examples.md                ← Before/after scenarios / 前后对比示例
├── install/
│   ├── claude-code.md         ← Claude Code installation / Claude Code 安装指南
│   ├── codex.md               ← Codex installation / Codex 安装指南
│   ├── gemini.md              ← Gemini installation / Gemini 安装指南
│   └── generic.md             ← Universal guide / 通用安装指南
└── LICENSE                    ← MIT
```

---

## Composability | 可组合性

Second-Order Thinking is a **cognitive base** — it changes how the agent reasons about consequences, not what it produces. It stacks cleanly with any domain skill (coding, design, writing, analysis) because it operates at a different layer.

二阶思维是一个**认知底座**——它改变 agent 推理后果的方式，而非产出内容。它与任何领域技能（编程、设计、写作、分析）无冲突地叠加，因为它运行在不同的层级。

### Relationship to other cognitive bases | 与其他认知底座的关系

| Layer 层级 | What it governs 管辖范围 | Example 示例 |
|---|---|---|
| [First Principles](https://github.com/d-wwei/first-principles) 第一性原理 | Input quality — what foundations conclusions are built on 输入质量 | "Audit assumptions before solving" 先审计假设 |
| Second-Order Thinking 二阶思维 | Consequence depth — how far forward conclusions are traced 后果深度 | "Trace 2-3 steps, then test the counterfactual" 追踪 2-3 步再测反事实 |
| [Results-Driven](https://github.com/d-wwei/results-driven) 以终为始 | Output quality — whether work is complete and verified 输出质量 | "Prove the outcome works" 证明结果可用 |

All load as always-on cognitive protocols. No conflicts. Combined: conclusions built on audited foundations, traced through multi-step consequences, and delivered with verified completeness.

三者同时加载，始终激活，互不冲突。组合效果：基于经过审计的基础、追踪多步后果、以经过验证的完整性交付的结论。

---

## Theoretical foundation | 理论基础

Synthesized from three traditions: Frederic Bastiat's "That Which Is Seen and That Which Is Not Seen" (1850) and Howard Marks' emphasis on second-level thinking in investing — both stress the discipline of asking "and then what?" beyond the obvious. Daniel Kahneman and Neal Roese's counterfactual thinking research — using "what if it hadn't happened?" as a causal reasoning tool. Mao Zedong's 星星之火可以燎原 — the observation that small forces under the right structural conditions can trigger nonlinear amplification, formalized as tipping-point detection.

综合三个传统：巴斯夏的"看得见的与看不见的"（1850）和霍华德·马克斯在投资中对二阶思考的强调——追问"然后呢？"；卡尼曼和罗斯的反事实思维研究——用"如果没发生会怎样？"作为因果推理工具；毛泽东的"星星之火，可以燎原"——小力量在适当结构条件下触发非线性放大。

The cognitive protocol strips all theory and translates these ideas into executable instructions for any reasoning agent.

认知协议剥离了所有理论，将这些思想转译为任何推理 agent 可执行的指令。

---

## License

MIT

---

## All Cognitive Bases

Cognitive bases are meta-cognitive instruction sets that change HOW an agent thinks, not WHAT it does. Each one targets a different cognitive axis. Mix and match.

| Cognitive Base | What it changes |
|---|---|
| [First Principles](https://github.com/d-wwei/first-principles) | Reason from verified foundations, not inherited conventions |
| [Results-Driven](https://github.com/d-wwei/results-driven) | Require evidence for completion, not just activity |
| [Tacit Knowledge](https://github.com/d-wwei/tacit-knowledge) | Think like an experienced practitioner |
| [Attention Allocation](https://github.com/d-wwei/attention-allocation) | Find and concentrate on the ONE binding constraint |
| [Bayesian Reasoning](https://github.com/d-wwei/bayesian-reasoning) | Calibrated probability thinking, not binary judgments |
| [Constraint as Catalyst](https://github.com/d-wwei/constraint-as-catalyst) | Turn constraints into innovation catalysts |
| [Conviction Override](https://github.com/d-wwei/conviction-override) | Override rational caution when obstacles are convention, not physics |
| [Cross-Domain Connector](https://github.com/d-wwei/cross-domain-connector) | Detect structural isomorphisms across disciplines |
| [Dialectical Thinking](https://github.com/d-wwei/dialectical-thinking) | Synthesize through contradictions (矛盾论) |
| [Double-Loop Learning](https://github.com/d-wwei/double-loop-learning) | Question the assumptions that produce errors |
| [Frame Auditing](https://github.com/d-wwei/frame-auditing) | Detect and transcend invisible analytical frames |
| [Interactive Cognition](https://github.com/d-wwei/interactive-cognition) | Model others' cognition and manage information flow |
| [Inversion Thinking](https://github.com/d-wwei/inversion-thinking) | Map failure modes first, then avoid them |
| [Motivation Audit](https://github.com/d-wwei/motivation-audit) | Audit motivational drivers before analysis (正心诚意) |
| [Non-Attachment](https://github.com/d-wwei/non-attachment) | Radical cognitive freedom — use frameworks without fusing |
| [Principled Action](https://github.com/d-wwei/principled-action) | Unify knowing and doing through practice-theory spirals (知行合一) |
| [Systems Thinking](https://github.com/d-wwei/systems-thinking) | Feedback-driven structural analysis, not linear cause-effect |
| [Temporal Wisdom](https://github.com/d-wwei/temporal-wisdom) | Make time your ally — compound effects and phase awareness |
| [Cognitive Base Creator](https://github.com/d-wwei/cognitive-base-creator) | Generate new cognitive bases from any thinking framework |
