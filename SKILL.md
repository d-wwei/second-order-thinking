# Second-Order Thinking

A cognitive base that shifts reasoning from "what happens next?" to "and then what? and then what?" — tracing consequences 2-3 steps forward, testing counterfactuals, and detecting nonlinear tipping points.

Not tied to any domain. Stacks with domain skills without conflict. Core rules are in `cognitive-protocol.md` (~30 lines, always-on). This file is the full reference framework.

---

## 1. Cognitive Shifts

### Shift 1: First consequence → Consequence chain

Default: Identify the immediate result and stop. "Lowering prices increases sales volume."
Target: Trace at least 2-3 steps. "Volume increases → margins shrink → competitors match price → volume gains erode → you're at the same market share but lower margins."

- For each consequence, ask: "And then what happens because of THAT?"
- At each step, estimate likelihood (high/medium/low) and magnitude (large/moderate/small).
- The chain often reveals that the 2nd or 3rd-order effect reverses the 1st-order benefit.

### Shift 2: Action analysis → Action vs. inaction analysis

Default: Evaluate the proposed action on its own merits. "This feature would improve retention."
Target: Compare against the null scenario. "If we don't build this, what happens to retention anyway?"

- The value of an action is not its absolute outcome; it's the delta between acting and not acting.
- Many "high value" actions look mediocre when the counterfactual is "the problem solves itself."
- Conversely, actions that seem modest may be critical if the counterfactual is rapid deterioration.

### Shift 3: Linear projection → Phase-transition detection

Default: Assume tomorrow looks like today, only more so. "We're growing 10% monthly, so in 12 months..."
Target: Identify where the curve bends — where linear becomes exponential or where growth hits a wall.

- **Amplification signals**: network effects, viral loops, compounding returns, trust cascading through a network.
- **Saturation signals**: market exhaustion, resource constraints, regulatory triggers, attention fatigue.
- **Tipping-point signals**: a small change that flips incentives, crosses a critical mass threshold, or activates a dormant feedback loop.
- Mao's 星星之火: the spark itself is not the story — the dry prairie is. Assess the conditions, not just the action.

---

## 2. Consequence Tracing Protocol

### Step 1: Map immediate consequences (Order 1)

List the direct, obvious results of the action. These are what everyone sees.

### Step 2: Trace forward (Order 2-3)

For each Order-1 consequence, ask: "What does this cause next?" Repeat once more for the most significant chains.

### Step 3: Rank chains

Not all chains matter equally. For each:
- **Likelihood**: How probable is this chain? (high / medium / low)
- **Magnitude**: How large is the impact if it occurs? (large / moderate / small)
- **Reversibility**: Can it be undone? Irreversible consequences deserve extra weight.
- Focus analysis on high-likelihood/large-magnitude chains. Acknowledge but don't over-analyze low/small ones.

### Step 4: Run the counterfactual

Repeat Steps 1-3 for the "do nothing" scenario. The decision value is the difference between the two paths.

### Step 5: Check for phase transitions

Scan the consequence chains for nonlinear jumps. If found, flag them as the dominant consideration — they often dwarf all linear effects.

### Stop rule

Stop tracing when consequences become speculative enough that two reasonable people would disagree on which direction they go. Name the point where you stopped and why. This prevents infinite regression without hiding behind it.

---

## 3. Anti-Pattern Checklist

1. **One-step stop** — Concluding after the immediate consequence without tracing further. Fix: force yourself to ask "and then what?" at least twice after the first answer.

2. **Infinite regression** — Tracing so far forward that every consequence branches into speculation. Fix: apply the stop rule — if reasonable people would disagree on the direction, you've gone far enough. Name where you stopped.

3. **Parallel listing** — Listing N possible 2nd-order consequences without ranking likelihood or magnitude. Fix: every listed consequence must carry a likelihood/magnitude tag. Unranked lists are not analysis.

4. **Ignoring counterfactual** — Analyzing "what happens if we do it" without analyzing "what happens if we don't." Fix: always run both paths. The delta is the decision, not the absolute outcome.

5. **Linear extrapolation** — Assuming the current trend continues at the same rate without considering bends, caps, or tipping points. Fix: for any multi-step projection, explicitly ask "where could this curve bend?" and "what structural change would alter the trajectory?"

---

## 4. Composing with Domain Skills

### Composition principles

1. Second-Order Thinking operates on **consequence depth** (how far you trace effects). Domain skills operate on **output format** (what you produce). No conflict.
2. When a domain skill provides a recommendation, Second-Order Thinking extends the analysis forward: "This recommendation is good in Order 1, but what happens in Order 2-3?"
3. Second-Order Thinking never overrides domain-specific safety constraints. Safety consequences are traced forward with extra weight on irreversibility.

### Stacking examples

- **With coding skill**: Before adding a feature, trace: Order 1 (solves user request), Order 2 (adds maintenance surface, changes API contract), Order 3 (future features must accommodate this, team velocity changes). Counterfactual: what happens if users use the existing workaround?
- **With business skill**: Before a pricing change, trace: Order 1 (revenue change), Order 2 (competitor response, customer behavior shift), Order 3 (market positioning, brand perception). Counterfactual: does the market shift without your action?
- **With writing skill**: Before structuring an argument, trace: Order 1 (reader gets the information), Order 2 (reader acts on it — how?), Order 3 (what does the reader's action cause?). Write for the 2nd-order reader response, not just comprehension.

### Relationship to First Principles

**Complementary, different axis.** First Principles governs what you reason FROM (are your foundations sound?). Second-Order Thinking governs how far you reason FORWARD (are you tracing consequences deeply enough?).

**Loading order**: First Principles loads first (audits the starting assumptions). Second-Order Thinking loads second (traces the consequences of conclusions built on those audited foundations). Combined effect: conclusions built on verified foundations AND traced through multi-step consequences.

**No conflict zones.** FP says "audit your assumptions" — SOT says "trace your conclusions forward." These are sequential: audit the input, produce the conclusion, then trace its consequences. FP asks "is this true?" — SOT asks "what happens because it's true?"

---

## 5. Intensity Calibration

### Full intensity — Irreversible decisions, strategic bets, policy design

Apply complete trace-counterfactual-transition cycle. Map 3 orders of consequences. Run full counterfactual. Scan for phase transitions. This is for: pricing changes, feature commitments, hiring decisions, market entry, policy proposals.

### Medium intensity — Significant but reversible decisions

Trace 2 orders of consequences. Quick counterfactual check ("what if we don't?"). Note any obvious nonlinear risks. This is for: sprint planning, process changes, resource allocation, vendor selection.

### Low intensity — Routine tasks, well-understood domains

Run the self-check silently. Only escalate if the self-check reveals a non-obvious 2nd-order effect. This is for: implementation tasks, standard operations, documentation, known-playbook execution.
