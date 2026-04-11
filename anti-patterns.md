# Second-Order Thinking (二阶思维) — Anti-Pattern Reference

5 reasoning failures specific to consequence tracing. Detect and rewrite immediately.

---

## 1. One-Step Stop

**Pattern**: Analyzing the immediate consequence and concluding, without asking "and then what?" The analysis looks complete because Order 1 is clear and confident — but the decision-relevant effects are hiding in Order 2-3.

**Detection**:
- The analysis names one consequence and immediately moves to a recommendation
- No sentence begins with "which leads to..." or "which then causes..."
- The conclusion could have been reached without any causal tracing at all
- Removing the word "therefore" from the output loses nothing

**Fix**: After your first consequence, force two more "and then what?" iterations. If the 2nd-order consequence reinforces the 1st-order conclusion, good — say so. If it undermines it, that's the insight.

```
"Should we hire two more engineers to speed up the release?"

One-step: "Yes — more engineers means faster velocity, and you'll hit your
Q3 deadline."

Second-order: "More engineers increases velocity in Q4, not Q3. In Q3,
onboarding slows the existing team — your current engineers spend 30% of
their time mentoring instead of building (Order 2). If the Q3 deadline is
the real constraint, the faster path is cutting scope, not adding headcount.
The new hires pay off in Q4 (Order 3) — which means the real question is
whether Q3 or Q4 is the binding deadline."
```

---

## 2. Infinite Regression

**Pattern**: Tracing consequences so far forward that every path branches into speculative scenarios. The analysis becomes exhaustive but useless — it covers everything and recommends nothing.

**Detection**:
- The consequence chain extends 5+ steps into the future
- Language shifts to "could potentially..." and "might eventually..."
- The analysis generates more questions than it answers
- A reader finishes the analysis knowing less about what to do than before
- Every chain ends with "it depends" or "this requires further analysis"

**Fix**: Apply the stop rule. Trace until two reasonable people would disagree on direction — that's your horizon. Name the stop point explicitly: "I'm tracing to Order 3 and stopping because beyond that, the outcome depends on competitor behavior we can't predict." The stop point itself is useful information.

```
"What happens if we open-source our core library?"

Infinite regression: "Competitors fork it, which could lead to ecosystem
fragmentation, which might cause developer confusion, which could reduce
adoption, which might force us to re-consolidate, which could damage trust
in the ecosystem, which might..." (continues for 12 branches)

Bounded trace: "Order 1: Developer adoption increases, competitors get
access. Order 2: Community contributions offset competitor gains (high
likelihood) — this is well-evidenced by Redis, Postgres, Linux precedent.
Order 3: Our competitive moat shifts from code to operational expertise
and ecosystem leadership. Stopping here — beyond Order 3, outcomes depend
on execution quality, which isn't a consequence to predict but a choice
to make."
```

---

## 3. Parallel Listing

**Pattern**: Listing multiple possible second-order consequences without ranking which are likely, which are large, and which actually matter for the decision. Gives the appearance of thorough analysis while avoiding the judgment call.

**Detection**:
- Consequences are presented as a bullet list with no ordering or weighting
- Words like "also," "additionally," "another possibility" appear without "most importantly" or "the dominant effect"
- The list has 5+ items and no item is marked as more significant than others
- A decision-maker reading the list cannot tell which consequence to plan for

**Fix**: Every consequence gets a likelihood/magnitude tag. Then sort by impact (likelihood x magnitude). Lead with the dominant chain. The others are acknowledged, not featured.

```
"What are the second-order effects of switching to a 4-day work week?"

Parallel listing:
- Employees might be more productive per hour
- Some projects might take longer
- Hiring might become easier
- Client expectations might need resetting
- Team collaboration might suffer
- Employee satisfaction might increase

Ranked analysis: "The dominant 2nd-order effect is hiring advantage (high
likelihood, large magnitude) — in a tight labor market, this changes your
candidate pipeline within 3 months. Secondary: per-hour productivity
increase (medium likelihood, moderate magnitude) — Perpetual Guardian's
trial showed 20% gains, but this varies by role. The client-expectation
risk is real but manageable (high likelihood, small magnitude) — it
requires a one-time communication, not an ongoing cost. Other effects
are low-magnitude noise."
```

---

## 4. Ignoring Counterfactual

**Pattern**: Analyzing the consequences of taking an action without analyzing the consequences of NOT taking it. This makes every action look justified because it's being compared against an invisible baseline of "nothing changes."

**Detection**:
- The word "if" appears only in "if we do X" constructions, never "if we don't do X"
- The baseline scenario is implicitly "everything stays the same"
- The analysis produces an absolute value ("this will increase revenue by $2M") rather than a delta ("this increases revenue by $2M vs. $1.5M we'd get from doing nothing")
- Inaction is treated as zero-cost by default

**Fix**: Always run the null scenario. Ask: "What happens if we do absolutely nothing?" Often the answer is "things improve anyway" (because other forces are at work) or "things deteriorate" (which changes the urgency calculus). The decision is always about the delta.

```
"Should we invest $500K in a marketing campaign to grow sign-ups?"

Without counterfactual: "The campaign will generate 10,000 new sign-ups
based on industry benchmarks. At our conversion rate, that's $800K in
ARR. Clear positive ROI."

With counterfactual: "Null scenario: organic sign-ups are currently
growing 8% month-over-month from word-of-mouth and SEO investments
landing. In 6 months, that's ~7,000 sign-ups without spending $500K.
The campaign's incremental value is 3,000 sign-ups (not 10,000), at
a cost of $167 per incremental sign-up. Is that worth it? Only if
those 3,000 extra users compound into something the organic 7,000 don't
— like hitting a network-effect threshold (Order 2). If yes, spend. If
they're just 3,000 more of the same, the $500K is better allocated
elsewhere."
```

---

## 5. Linear Extrapolation

**Pattern**: Projecting current trends forward without considering where the curve bends — where growth saturates, where feedback loops activate, where small changes flip the system into a different state.

**Detection**:
- Phrases like "at this rate, in 12 months we'll..."
- Growth projections that don't name an upper bound or inflection point
- Decline projections that don't consider intervention triggers
- No mention of what structural change could alter the trajectory
- The word "exponential" used but no saturation point identified

**Fix**: For any projection beyond 2 steps, explicitly ask: "Where does this curve bend?" Name the structural force that would cause the bend — market saturation, resource constraint, competitor response, regulatory trigger, or feedback loop activation. Mao's 星星之火 works both ways: conditions that amplify also eventually saturate.

```
"Our user base is growing 15% monthly. Project 12-month revenue."

Linear extrapolation: "At 15% monthly growth, you'll have 5.4x current
users in 12 months. Revenue scales proportionally to $16.2M."

Phase-transition aware: "15% monthly growth will continue until you
exhaust your initial segment — likely around month 5-6 when you saturate
early adopters (Order 2). Then growth depends on crossing the chasm to
mainstream users, which historically drops growth to 3-5% without a product
shift. Meanwhile, if you hit 50K users (around month 4 at current rate),
network effects activate — each user inviting 1.2 others creates a
compounding loop that could temporarily spike growth to 25% before
saturation kicks in. Realistic 12-month range: $8M-$14M depending on
whether you cross the chasm, not $16.2M from linear projection."
```

---

## Quick Self-Check Sequence

After completing any analysis, scan in this order:

1. **Depth** → Did I stop after the first consequence? (Anti-pattern 1: one-step stop)
2. **Boundary** → Am I tracing past the actionable horizon? (Anti-pattern 2: infinite regression)
3. **Ranking** → Did I rank consequences or just list them? (Anti-pattern 3: parallel listing)
4. **Null path** → Did I analyze what happens if we do nothing? (Anti-pattern 4: ignoring counterfactual)
5. **Curve** → Am I assuming the trend continues in a straight line? (Anti-pattern 5: linear extrapolation)
